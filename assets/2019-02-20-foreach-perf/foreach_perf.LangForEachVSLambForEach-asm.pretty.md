## .NET Framework 4.7.2 (CLR 4.0.30319.42000), 32bit LegacyJIT-v4.7.3324.0
```assembly
; foreach_perf.LangForEachVSLambForEach.LambForEach()
                   stringField.ForEach(x => x.Clear());
            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
       IL_0000: ldarg.0
       IL_0001: ldfld System.Collections.Generic.List`1<System.Text.StringBuilder> foreach_perf.LangForEachVSLambForEach::stringField
       IL_0006: ldsfld System.Action`1<System.Text.StringBuilder> foreach_perf.LangForEachVSLambForEach/<>c::<>9__2_0
       IL_000b: dup
       IL_000c: brtrue.s IL_0025
       IL_000e: pop
       IL_000f: ldsfld foreach_perf.LangForEachVSLambForEach/<>c foreach_perf.LangForEachVSLambForEach/<>c::<>9
       IL_0014: ldftn System.Void foreach_perf.LangForEachVSLambForEach/<>c::<LambForEach>b__2_0(System.Text.StringBuilder)
       IL_001a: newobj System.Void System.Action`1<System.Text.StringBuilder>::.ctor(System.Object,System.IntPtr)
       mov     ebx,dword ptr [edi+4]
       mov     eax,dword ptr ds:[04015770h]
       mov     ecx,ebx
       mov     edx,eax
       test    eax,eax
       jne     M00_L01
       mov     ecx,1565780h
       call    015630c8
       mov     esi,eax
       mov     eax,dword ptr ds:[0401576Ch]
       mov     dword ptr [ebp-10h],eax
       test    eax,eax
       jne     M00_L00
       mov     ecx,esi
       call    System.MulticastDelegate.ThrowNullThisInDelegateToInstance()
M00_L00:
       mov     eax,dword ptr [ebp-10h]
       lea     edx,[esi+4]
       call    clr+0xe780
       mov     eax,5522B60h
       mov     dword ptr [esi+0Ch],eax
                   return stringField.Count;
            ^^^^^^^^^^^^^^^^^^^^^^^^^
       IL_001f: dup
       IL_0020: stsfld System.Action`1<System.Text.StringBuilder> foreach_perf.LangForEachVSLambForEach/<>c::<>9__2_0
       lea     edx,ds:[4015770h]
       call    clr+0xe810
       mov     ecx,ebx
       mov     edx,esi
M00_L01:
       cmp     dword ptr [ecx],ecx
       IL_0025: callvirt System.Void System.Collections.Generic.List`1<System.Text.StringBuilder>::ForEach(System.Action`1<!0>)
       call    System.Collections.Generic.List`1[[System.__Canon, mscorlib]].ForEach(System.Action`1<System.__Canon>)
       IL_002a: ldarg.0
       IL_002b: ldfld System.Collections.Generic.List`1<System.Text.StringBuilder> foreach_perf.LangForEachVSLambForEach::stringField
       IL_0030: callvirt System.Int32 System.Collections.Generic.List`1<System.Text.StringBuilder>::get_Count()
       IL_0035: ret
       mov     eax,dword ptr [edi+4]
       mov     eax,dword ptr [eax+0Ch]
; Total bytes of code 94
```
```assembly
; System.MulticastDelegate.ThrowNullThisInDelegateToInstance()
       IL_000a: newobj System.Void System.ArgumentException::.ctor(System.String)
       call    System.ArgumentException..ctor(System.String)
       IL_000f: throw
       mov     ecx,dword ptr [ebp-4]
       call    mscorlib_ni+0x31b090
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       mov     eax,edx
       lea     edx,[ecx+4]
       call    mscorlib_ni+0x31b010
       mov     eax,dword ptr [esp+4]
       mov     dword ptr [ecx+0Ch],eax
; Total bytes of code 38
```
```assembly
; System.Collections.Generic.List`1[[System.__Canon, mscorlib]].ForEach(System.Action`1<System.__Canon>)
       IL_0000: ldarg.1
       IL_0001: brtrue.s IL_0009
       test    ebx,ebx
       jne     System_Core_ni+0x3bc89c
       IL_0003: ldc.i4.8
       IL_0004: call System.Void System.ThrowHelper::ThrowArgumentNullException(System.ExceptionArgument)
       mov     ecx,dword ptr [System_Core_ni+0x51624
       call    System_Core_ni+0x19dda8
       mov     esi,eax
       mov     ecx,8
       call    System_Core_ni+0x19c2c0
       mov     edx,eax
       mov     ecx,esi
       call    System_Core_ni+0x19c2c8
       mov     ecx,esi
       call    System_Core_ni+0x19de18
       IL_0009: ldarg.0
       IL_000a: ldfld System.Int32 System.Collections.Generic.List`1<T>::_version
       IL_000f: stloc.0
       mov     eax,dword ptr [esi+10h]
       mov     dword ptr [ebp-10h],eax
       IL_0010: ldc.i4.0
       IL_0011: stloc.1
       IL_0012: br.s IL_003a
       xor     edi,edi
       IL_003a: ldloc.1
       IL_003b: ldarg.0
       IL_003c: ldfld System.Int32 System.Collections.Generic.List`1<T>::_size
       IL_0041: blt.s IL_0014
       cmp     dword ptr [esi+0Ch],0
       jle     System_Core_ni+0x3bc8fa
       mov     ecx,1
       mov     edx,6ECh
       call    System_Core_ni+0x19dd98
       mov     dword ptr [ebp-14h],eax
       IL_0014: ldloc.0
       IL_0015: ldarg.0
       IL_0016: ldfld System.Int32 System.Collections.Generic.List`1<T>::_version
       IL_001b: beq.s IL_0024
       IL_001d: call System.Boolean System.Runtime.Versioning.BinaryCompatibility::get_TargetsAtLeast_Desktop_V4_5()
       IL_0022: brtrue.s IL_0043
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+10h]
       je      System_Core_ni+0x3bc8d3
       mov     eax,dword ptr [ebp-14h]
       mov     edx,dword ptr [eax+0BE0h]
       cmp     byte ptr [edx+7],0
       jne     System_Core_ni+0x3bc8fa
       IL_0024: ldarg.1
       IL_0025: ldarg.0
       IL_0026: ldfld T[] System.Collections.Generic.List`1<T>::_items
       IL_002b: ldloc.1
       IL_002c: ldelem.any T
       mov     eax,dword ptr [esi+4]
       cmp     edi,dword ptr [eax+4]
       jae     System_Core_ni+0x3bc932
       lea     edx,[edi+edi*2]
       lea     eax,[eax+edx*4+8]
       push    dword ptr [eax+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,ebx
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       IL_0031: callvirt System.Void System.Action`1<T>::Invoke(T)
       call    eax
       IL_0036: ldloc.1
       IL_0037: ldc.i4.1
       IL_0038: add
       IL_0039: stloc.1
       inc     edi
       cmp     edi,dword ptr [esi+0Ch]
       jl      System_Core_ni+0x3bc8bc
       IL_0043: ldloc.0
       IL_0044: ldarg.0
       IL_0045: ldfld System.Int32 System.Collections.Generic.List`1<T>::_version
       IL_004a: beq.s IL_005a
       IL_004c: call System.Boolean System.Runtime.Versioning.BinaryCompatibility::get_TargetsAtLeast_Desktop_V4_5()
       IL_0051: brfalse.s IL_005a
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+10h]
       je      System_Core_ni+0x3bc92a
       mov     ecx,1
       mov     edx,6ECh
       call    System_Core_ni+0x19dd98
       mov     dword ptr [ebp-14h],eax
       mov     edx,dword ptr [eax+0BE0h]
       cmp     byte ptr [edx+7],0
       je      System_Core_ni+0x3bc92a
       IL_0053: ldc.i4.s 32
       mov     ecx,20h
       IL_0055: call System.Void System.ThrowHelper::ThrowInvalidOperationException(System.ExceptionResource)
       call    System_Core_ni+0x19c340
       IL_005a: ret
       lea     esp,[ebp-0Ch]
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    System_Core_ni+0x19de20
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     System_Core_ni+0x3bc973
       mov     ecx,dword ptr [System_Core_ni+0x51624
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       sub     esp,8
       mov     esi,ecx
       mov     ebx,edx
       test    ebx,ebx
       jne     System_Core_ni+0x498de0
       mov     ecx,dword ptr [System_Core_ni+0x51624
       call    System_Core_ni+0x19dda8
       mov     esi,eax
       mov     ecx,8
       call    System_Core_ni+0x19c2c0
       mov     edx,eax
       mov     ecx,esi
       call    System_Core_ni+0x19c2c8
       mov     ecx,esi
       call    System_Core_ni+0x19de18
       mov     eax,dword ptr [esi+10h]
       mov     dword ptr [ebp-10h],eax
       xor     edi,edi
       cmp     dword ptr [esi+0Ch],0
       jle     System_Core_ni+0x498e38
       mov     ecx,1
       mov     edx,6ECh
       call    System_Core_ni+0x19dd98
       mov     dword ptr [ebp-14h],eax
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+10h]
       je      System_Core_ni+0x498e17
       mov     eax,dword ptr [ebp-14h]
       mov     edx,dword ptr [eax+0BE0h]
       cmp     byte ptr [edx+7],0
       jne     System_Core_ni+0x498e38
       mov     eax,dword ptr [esi+4]
       cmp     edi,dword ptr [eax+4]
       jae     System_Core_ni+0x498e70
       lea     eax,[eax+edi*8+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,ebx
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     edi
       cmp     edi,dword ptr [esi+0Ch]
       jl      System_Core_ni+0x498e00
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+10h]
       je      System_Core_ni+0x498e68
       mov     ecx,1
       mov     edx,6ECh
       call    System_Core_ni+0x19dd98
       mov     dword ptr [ebp-14h],eax
       mov     edx,dword ptr [eax+0BE0h]
       cmp     byte ptr [edx+7],0
       je      System_Core_ni+0x498e68
       mov     ecx,20h
       call    System_Core_ni+0x19c340
       lea     esp,[ebp-0Ch]
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    System_Core_ni+0x19de20
       int     3
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     System_Core_ni+0x498eb3
       mov     ecx,dword ptr [System_Core_ni+0x51624
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       sub     esp,8
       mov     esi,ecx
       mov     ebx,edx
       test    ebx,ebx
       jne     System_Core_ni+0x51f9c0
       mov     ecx,dword ptr [System_Core_ni+0x51624
       call    System_Core_ni+0x19dda8
       mov     esi,eax
       mov     ecx,8
       call    System_Core_ni+0x19c2c0
       mov     edx,eax
       mov     ecx,esi
       call    System_Core_ni+0x19c2c8
       mov     ecx,esi
       call    System_Core_ni+0x19de18
       mov     eax,dword ptr [esi+10h]
       mov     dword ptr [ebp-10h],eax
       xor     edi,edi
       cmp     dword ptr [esi+0Ch],0
       jle     System_Core_ni+0x51fa24
       mov     ecx,1
       mov     edx,6ECh
       call    System_Core_ni+0x19dd98
       mov     dword ptr [ebp-14h],eax
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+10h]
       je      System_Core_ni+0x51f9f7
       mov     eax,dword ptr [ebp-14h]
       mov     edx,dword ptr [eax+0BE0h]
       cmp     byte ptr [edx+7],0
       jne     System_Core_ni+0x51fa24
       mov     eax,dword ptr [esi+4]
       cmp     edi,dword ptr [eax+4]
       jae     System_Core_ni+0x51fa5c
       lea     edx,[edi+edi*4]
       lea     eax,[eax+edx*4+8]
       push    dword ptr [eax+10h]
       push    dword ptr [eax+0Ch]
       push    dword ptr [eax+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,ebx
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     edi
       cmp     edi,dword ptr [esi+0Ch]
       jl      System_Core_ni+0x51f9e0
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+10h]
       je      System_Core_ni+0x51fa54
       mov     ecx,1
       mov     edx,6ECh
       call    System_Core_ni+0x19dd98
       mov     dword ptr [ebp-14h],eax
       mov     edx,dword ptr [eax+0BE0h]
       cmp     byte ptr [edx+7],0
       je      System_Core_ni+0x51fa54
       mov     ecx,20h
       call    System_Core_ni+0x19c340
       lea     esp,[ebp-0Ch]
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    System_Core_ni+0x19de20
       int     3
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     System_Core_ni+0x51fa9f
       mov     ecx,dword ptr [System_Core_ni+0x51624
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       sub     esp,8
       mov     esi,ecx
       mov     ebx,edx
       test    ebx,ebx
       jne     System_Core_ni+0x557244
       mov     ecx,dword ptr [System_Core_ni+0x51624
       call    System_Core_ni+0x19dda8
       mov     esi,eax
       mov     ecx,8
       call    System_Core_ni+0x19c2c0
       mov     edx,eax
       mov     ecx,esi
       call    System_Core_ni+0x19c2c8
       mov     ecx,esi
       call    System_Core_ni+0x19de18
       mov     eax,dword ptr [esi+10h]
       mov     dword ptr [ebp-10h],eax
       xor     edi,edi
       cmp     dword ptr [esi+0Ch],0
       jle     System_Core_ni+0x55729c
       mov     ecx,1
       mov     edx,6ECh
       call    System_Core_ni+0x19dd98
       mov     dword ptr [ebp-14h],eax
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+10h]
       je      System_Core_ni+0x55727b
       mov     eax,dword ptr [ebp-14h]
       mov     edx,dword ptr [eax+0BE0h]
       cmp     byte ptr [edx+7],0
       jne     System_Core_ni+0x55729c
       mov     eax,dword ptr [esi+4]
       cmp     edi,dword ptr [eax+4]
       jae     System_Core_ni+0x5572d4
       lea     eax,[eax+edi*8+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,ebx
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     edi
       cmp     edi,dword ptr [esi+0Ch]
       jl      System_Core_ni+0x557264
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+10h]
       je      System_Core_ni+0x5572cc
       mov     ecx,1
       mov     edx,6ECh
       call    System_Core_ni+0x19dd98
       mov     dword ptr [ebp-14h],eax
       mov     edx,dword ptr [eax+0BE0h]
       cmp     byte ptr [edx+7],0
       je      System_Core_ni+0x5572cc
       mov     ecx,20h
       call    System_Core_ni+0x19c340
       lea     esp,[ebp-0Ch]
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    System_Core_ni+0x19de20
       int     3
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     System_Core_ni+0x557317
       mov     ecx,dword ptr [System_Core_ni+0x51624
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       sub     esp,8
       mov     esi,ecx
       mov     ebx,edx
       test    ebx,ebx
       jne     System_ni+0x772280
       mov     ecx,dword ptr [System_ni+0x5607c
       call    System_ni+0x1492a0
       mov     esi,eax
       mov     ecx,8
       call    System_ni+0x146c88
       mov     edx,eax
       mov     ecx,esi
       call    System_ni+0x1465a8
       mov     ecx,esi
       call    System_ni+0x1492c8
       mov     eax,dword ptr [esi+10h]
       mov     dword ptr [ebp-10h],eax
       xor     edi,edi
       cmp     dword ptr [esi+0Ch],0
       jle     System_ni+0x7722d8
       mov     ecx,1
       mov     edx,6ECh
       call    System_ni+0x149290
       mov     dword ptr [ebp-14h],eax
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+10h]
       je      System_ni+0x7722b7
       mov     eax,dword ptr [ebp-14h]
       mov     edx,dword ptr [eax+0BE0h]
       cmp     byte ptr [edx+7],0
       jne     System_ni+0x7722d8
       mov     eax,dword ptr [esi+4]
       cmp     edi,dword ptr [eax+4]
       jae     System_ni+0x772310
       lea     eax,[eax+edi*8+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,ebx
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     edi
       cmp     edi,dword ptr [esi+0Ch]
       jl      System_ni+0x7722a0
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+10h]
       je      System_ni+0x772308
       mov     ecx,1
       mov     edx,6ECh
       call    System_ni+0x149290
       mov     dword ptr [ebp-14h],eax
       mov     edx,dword ptr [eax+0BE0h]
       cmp     byte ptr [edx+7],0
       je      System_ni+0x772308
       mov     ecx,20h
       call    System_ni+0x146878
       lea     esp,[ebp-0Ch]
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    System_ni+0x149310
       int     3
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     System_ni+0x772353
       mov     ecx,dword ptr [System_ni+0x5607c
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       sub     esp,8
       mov     esi,ecx
       mov     ebx,edx
       test    ebx,ebx
       jne     System_ni+0x784a80
       mov     ecx,dword ptr [System_ni+0x5607c
       call    System_ni+0x1492a0
       mov     esi,eax
       mov     ecx,8
       call    System_ni+0x146c88
       mov     edx,eax
       mov     ecx,esi
       call    System_ni+0x1465a8
       mov     ecx,esi
       call    System_ni+0x1492c8
       mov     eax,dword ptr [esi+10h]
       mov     dword ptr [ebp-10h],eax
       xor     edi,edi
       cmp     dword ptr [esi+0Ch],0
       jle     System_ni+0x784ad3
       mov     ecx,1
       mov     edx,6ECh
       call    System_ni+0x149290
       mov     dword ptr [ebp-14h],eax
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+10h]
       je      System_ni+0x784ab7
       mov     eax,dword ptr [ebp-14h]
       mov     edx,dword ptr [eax+0BE0h]
       cmp     byte ptr [edx+7],0
       jne     System_ni+0x784ad3
       mov     eax,dword ptr [esi+4]
       cmp     edi,dword ptr [eax+4]
       jae     System_ni+0x784b0b
       mov     edx,dword ptr [eax+edi*4+8]
       mov     ecx,ebx
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     edi
       cmp     edi,dword ptr [esi+0Ch]
       jl      System_ni+0x784aa0
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+10h]
       je      System_ni+0x784b03
       mov     ecx,1
       mov     edx,6ECh
       call    System_ni+0x149290
       mov     dword ptr [ebp-14h],eax
       mov     edx,dword ptr [eax+0BE0h]
       cmp     byte ptr [edx+7],0
       je      System_ni+0x784b03
       mov     ecx,20h
       call    System_ni+0x146878
       lea     esp,[ebp-0Ch]
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    System_ni+0x149310
       int     3
       int     3
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     System_ni+0x784b4f
       mov     ecx,dword ptr [System_ni+0x5607c
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x1002f76
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0x3a2050
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x1002f48
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x1002f9c
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x1002fc0
       mov     edx,dword ptr [edx+eax*4+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0x3a2050
       jmp     mscorlib_ni+0x3a2041
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       sub     esp,0Ch
       mov     edi,ecx
       mov     ebx,edx
       test    ebx,ebx
       je      mscorlib_ni+0x1002fc8
       shufps  xmm0,xmmword ptr [eax],33h
       imul    bl
       jmp     mscorlib_ni+0x3a20ac
       add     esi,1
       cmp     esi,dword ptr [edi+0Ch]
       jge     mscorlib_ni+0x3a20cf
       mov     eax,dword ptr [edi+4]
       cmp     esi,dword ptr [eax+4]
       jae     mscorlib_ni+0x1002fee
       mov     edx,dword ptr [eax+esi*4+8]
       mov     ecx,ebx
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       test    eax,eax
       je      mscorlib_ni+0x3a20a9
       cmp     esi,dword ptr [edi+0Ch]
       jl      mscorlib_ni+0x3a213a
       xor     eax,eax
       lea     esp,[ebp-0Ch]
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [edi+0Ch]
       jge     mscorlib_ni+0x3a2107
       mov     edx,dword ptr [edi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x1002fee
       mov     edx,dword ptr [edx+eax*4+8]
       push    esp
       or      byte ptr [eax],8Bh
       retf
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       test    eax,eax
       jne     mscorlib_ni+0x3a20de
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [edi+0Ch]
       jl      mscorlib_ni+0x3a2142
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [edi+0Ch]
       jl      mscorlib_ni+0x3a20e1
       mov     ecx,dword ptr [edi+4]
       mov     eax,dword ptr [edi+0Ch]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x107362a
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xb9a940
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10735fc
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x1073650
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x1073674
       lea     eax,[edx+eax*8+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xb9a940
       jmp     mscorlib_ni+0xb9a931
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xb9a9ea
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       popad
       js      mscorlib_ni+0xb9a9a1
       mov     ebx,eax
       mov     ecx,4A49h
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xb9a9f9
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xb9aa16
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xb9aa16
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xb9aa16
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x1080eae
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xbf8480
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x1080e80
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x1080ed4
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x1080ef8
       lea     eax,[edx+eax*8+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xbf8480
       jmp     mscorlib_ni+0xbf8471
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xbf852a
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       test    byte ptr [ebp-2774008Eh],0B9h
       dec     ecx
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xbf8539
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xbf8556
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xbf8556
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xbf8556
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x108d2b2
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xc43310
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x108d284
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x108d2d8
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x108d2fc
       mov     edx,dword ptr [edx+eax*4+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xc43310
       jmp     mscorlib_ni+0xc43301
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xc433b6
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       mov     ecx,8
       add     byte ptr [eax],al
       call    System.ThrowHelper.GetArgumentName(System.ExceptionArgument)
       mov     ebx,eax
       mov     ecx,4A49h
       dec     ecx
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jne     mscorlib_ni+0xc433d0
       adc     al,83h
       sti
       push    dword ptr [ecx-47h]
       push    cs
       add     byte ptr [eax],al
       add     byte ptr [ebp+5EE80851h],cl
       mov     ebx,12EBFFEDh
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xc433e2
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x108d68a
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xc44790
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x108d65c
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x108d6b0
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x108d6d4
       lea     eax,[edx+eax*8+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xc44790
       jmp     mscorlib_ni+0xc44781
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xc4483a
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       out     0C2h,al
       ins     dword ptr es:[edi],dx
       dec     dword ptr [ebx+4A49B9D8h]
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xc44849
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xc44866
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xc44866
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xc44866
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x108db82
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xc46430
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x108db54
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x108dba8
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x108dbcc
       push    dword ptr [edx+eax*8+0Ch]
       push    dword ptr [edx+eax*8+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xc46430
       jmp     mscorlib_ni+0xc46421
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xc464da
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       mov     ecx,8
       add     byte ptr [eax],al
       call    System.ThrowHelper.GetArgumentName(System.ExceptionArgument)
       mov     ebx,eax
       mov     ecx,4A49h
       dec     ecx
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jne     mscorlib_ni+0xc464f4
       adc     al,83h
       sti
       push    dword ptr [ecx-47h]
       push    cs
       add     byte ptr [eax],al
       add     byte ptr [ebp+3AE80851h],cl
       mov     ch,ch
       ???
       jmp     mscorlib_ni+0xc46506
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xc46506
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x1091d06
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xc707e0
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x1091cd8
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x1091d2c
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x1091d50
       movzx   edx,byte ptr [edx+eax+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xc707e0
       jmp     mscorlib_ni+0xc707d1
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xc70886
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       call    B9D8:8BFF6B02
       dec     ecx
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xc70895
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xc708b2
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xc708b2
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xc708b2
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10a5c6e
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xd0a1e0
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10a5c40
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10a5c94
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10a5cb8
       imul    ecx,eax,1Ch
       lea     edx,[edx+ecx+8]
       push    dword ptr [edx+18h]
       push    dword ptr [edx+14h]
       push    dword ptr [edx+10h]
       push    dword ptr [edx+0Ch]
       push    dword ptr [edx+8]
       push    dword ptr [edx+4]
       push    dword ptr [edx]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xd0a1e0
       jmp     mscorlib_ni+0xd0a1d1
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xd0a29e
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       dec     dword ptr [ebx+8B9F0h]
       add     byte ptr [eax],al
       add     al,ch
       sub     byte ptr [eax+61h],0FFh
       mov     ebx,eax
       mov     ecx,4A49h
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       inc     dword ptr msvcrt!modf+0x175f
       jne     mscorlib_ni+0xd0a2b8
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xd0a2ca
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xd0a2ca
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xd0a2ca
       mov     ecx,0Eh
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10aba9e
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xd53270
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10aba70
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10abac4
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10abae8
       lea     eax,[edx+eax*8+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xd53270
       jmp     mscorlib_ni+0xd53261
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xd5331a
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       push    es
       fcomp   dword ptr [edi+edi*8-75h]
       fdivr   dword ptr [ecx+4A49h]
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xd53329
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xd53346
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xd53346
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xd53346
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10ac00a
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xd56cf0
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10abfdc
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10ac030
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10ac054
       movsx   edx,word ptr [edx+eax*2+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xd56cf0
       jmp     mscorlib_ni+0xd56ce1
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xd56d96
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       mov     bl,byte ptr [ebp-277400A4h]
       mov     ecx,4A49h
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xd56da5
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xd56dc2
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xd56dc2
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xd56dc2
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10ad49a
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xd65ac0
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10ad46c
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10ad4c0
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10ad4e4
       movzx   edx,byte ptr [edx+eax+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xd65ac0
       jmp     mscorlib_ni+0xd65ab1
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xd65b66
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       mov     edx,8BFF5BAFh
       fdivr   dword ptr [ecx+4A49h]
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xd65b75
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xd65b92
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xd65b92
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xd65b92
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10ade2a
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xd7b010
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10addfc
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10ade50
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10ade74
       lea     eax,[edx+eax*8+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xd7b010
       jmp     mscorlib_ni+0xd7b001
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xd7b0ba
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       pop     dx
       pop     edx
       dec     dword ptr [ebx+4A49B9D8h]
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xd7b0c9
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xd7b0e6
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xd7b0e6
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xd7b0e6
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10aed26
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xd81960
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10aecf8
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10aed4c
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10aed70
       lea     eax,[edx+eax*8+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xd81960
       jmp     mscorlib_ni+0xd81951
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xd81a0a
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       push    ss
       ???
       pop     ecx
       dec     dword ptr [ebx+4A49B9D8h]
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xd81a19
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xd81a36
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xd81a36
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xd81a36
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10b13aa
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xd93af0
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10b137c
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10b13d0
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10b13f4
       movzx   edx,word ptr [edx+eax*2+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xd93af0
       jmp     mscorlib_ni+0xd93ae1
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xd93b96
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       mov     cl,bh
       pop     eax
       dec     dword ptr [ebx+4A49B9D8h]
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xd93ba5
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xd93bc2
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xd93bc2
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xd93bc2
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10b37d6
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xda47b0
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10b37a8
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10b37fc
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10b3820
       lea     ecx,[eax+eax*4]
       lea     edx,[edx+ecx*4+8]
       push    dword ptr [edx+10h]
       push    dword ptr [edx+0Ch]
       push    dword ptr [edx+8]
       push    dword ptr [edx+4]
       push    dword ptr [edx]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xda47b0
       jmp     mscorlib_ni+0xda47a1
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xda4866
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       mov     edx,8BFF57C2h
       fdivr   dword ptr [ecx+4A49h]
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xda4875
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xda4892
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xda4892
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xda4892
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10b4446
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xda99e0
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10b4418
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10b446c
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10b4490
       mov     edx,dword ptr [edx+eax*4+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xda99e0
       jmp     mscorlib_ni+0xda99d1
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xda9a86
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       mov     ecx,8
       add     byte ptr [eax],al
       call    System.ThrowHelper.GetArgumentName(System.ExceptionArgument)
       mov     ebx,eax
       mov     ecx,4A49h
       dec     ecx
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jne     mscorlib_ni+0xda9aa0
       adc     al,83h
       sti
       push    dword ptr [ecx-47h]
       push    cs
       add     byte ptr [eax],al
       add     byte ptr [ebp-7117F7AFh],cl
       push    esp
       xlat    byte ptr [ebx]
       ???
       jmp     mscorlib_ni+0xda9ab2
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xda9ab2
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10b5c0e
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xdb3620
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10b5be0
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10b5c34
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10b5c58
       lea     ecx,[eax+eax*2]
       lea     edx,[edx+ecx*4+8]
       push    dword ptr [edx+8]
       push    dword ptr [edx+4]
       push    dword ptr [edx]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xdb3620
       jmp     mscorlib_ni+0xdb3611
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xdb36d2
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       dec     dword ptr [ebx+8B9F0h]
       add     byte ptr [eax],al
       add     al,ch
       dec     esi
       aamb    56h
       dec     dword ptr [ebx+4A49B9D8h]
       mov     ecx,4A49h
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       inc     dword ptr msvcrt!modf+0x175f
       jne     mscorlib_ni+0xdb36ec
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xdb36fe
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xdb36fe
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xdb36fe
       mov     ecx,0Eh
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10b6f72
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xdbb910
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10b6f44
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10b6f98
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10b6fbc
       lea     eax,[edx+eax*8+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xdbb910
       jmp     mscorlib_ni+0xdbb901
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xdbb9ba
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       push    cx
       push    esi
       dec     dword ptr [ebx+4A49B9D8h]
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xdbb9c9
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xdbb9e6
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xdbb9e6
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xdbb9e6
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10b8fea
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xdcaf60
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10b8fbc
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10b9010
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10b9034
       movsx   edx,byte ptr [edx+eax+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xdcaf60
       jmp     mscorlib_ni+0xdcaf51
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xdcb006
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       sbb     bl,byte ptr [ebx+55h]
       dec     dword ptr [ebx+4A49B9D8h]
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xdcb015
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xdcb032
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xdcb032
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xdcb032
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10b9802
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xdcf780
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10b97d4
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10b9828
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10b984c
       lea     ecx,[eax+eax*2]
       lea     edx,[edx+ecx*4+8]
       push    dword ptr [edx+8]
       push    dword ptr [edx+4]
       push    dword ptr [edx]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xdcf780
       jmp     mscorlib_ni+0xdcf771
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xdcf832
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       dec     dword ptr [ebx+8B9F0h]
       add     byte ptr [eax],al
       add     al,ch
       out     dx,al
       adc     dl,byte ptr [ebp-1]
       mov     ebx,eax
       mov     ecx,4A49h
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       inc     dword ptr msvcrt!modf+0x175f
       jne     mscorlib_ni+0xdcf84c
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xdcf85e
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xdcf85e
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xdcf85e
       mov     ecx,0Eh
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10bab22
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xdd8530
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10baaf4
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10bab48
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10bab6c
       lea     eax,[edx+eax*8+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xdd8530
       jmp     mscorlib_ni+0xdd8521
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xdd85da
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       inc     esi
       test    dword ptr [edi+edi*8-75h],edx
       fdivr   dword ptr [ecx+4A49h]
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xdd85e9
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xdd8606
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xdd8606
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xdd8606
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10bb1d6
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xddc720
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10bb1a8
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10bb1fc
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10bb220
       lea     ecx,[eax+eax*2]
       lea     edx,[edx+ecx*4+8]
       push    dword ptr [edx+8]
       push    dword ptr [edx+4]
       push    dword ptr [edx]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xddc720
       jmp     mscorlib_ni+0xddc711
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xddc7d2
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       dec     dword ptr [ebx+8B9F0h]
       add     byte ptr [eax],al
       add     al,ch
       dec     esi
       inc     ebx
       push    esp
       dec     dword ptr [ebx+4A49B9D8h]
       mov     ecx,4A49h
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       inc     dword ptr msvcrt!modf+0x175f
       jne     mscorlib_ni+0xddc7ec
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xddc7fe
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xddc7fe
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xddc7fe
       mov     ecx,0Eh
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10bdf42
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xdf0b10
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10bdf14
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10bdf68
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10bdf8c
       lea     eax,[edx+eax*8+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xdf0b10
       jmp     mscorlib_ni+0xdf0b01
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xdf0bba
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       call    word ptr [edx-1]
       mov     ebx,eax
       mov     ecx,4A49h
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xdf0bc9
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xdf0be6
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xdf0be6
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xdf0be6
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10be9be
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xdf4f60
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10be990
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10be9e4
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10bea08
       push    dword ptr [edx+eax*8+0Ch]
       push    dword ptr [edx+eax*8+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xdf4f60
       jmp     mscorlib_ni+0xdf4f51
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xdf500a
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       mov     ecx,8
       add     byte ptr [eax],al
       call    System.ThrowHelper.GetArgumentName(System.ExceptionArgument)
       mov     ebx,eax
       mov     ecx,4A49h
       dec     ecx
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jne     mscorlib_ni+0xdf5024
       adc     al,83h
       sti
       push    dword ptr [ecx-47h]
       push    cs
       add     byte ptr [eax],al
       add     byte ptr [ebp+0AE80851h],cl
       lahf
       sar     bh,cl
       jmp     mscorlib_ni+0xdf5036
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xdf5036
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10bfe32
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xdfd1b0
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10bfe04
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10bfe58
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10bfe7c
       shl     eax,4
       lea     eax,[edx+eax+8]
       push    dword ptr [eax+0Ch]
       push    dword ptr [eax+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xdfd1b0
       jmp     mscorlib_ni+0xdfd1a1
       int     3
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xdfd266
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       push    ecx
       dec     dword ptr [ebx+8B9F0h]
       or      byte ptr [eax],al
       add     byte ptr [eax],al
       call    System.ThrowHelper.GetArgumentName(System.ExceptionArgument)
       mov     ebx,eax
       fdivr   dword ptr [ecx+4A49h]
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       push    ecx
       inc     dword ptr msvcrt!modf+0x175f
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xdfd292
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xdfd292
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xdfd292
       mov     ecx,0Eh
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10c0502
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xe01b90
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c04d4
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c0528
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10c054c
       mov     edx,dword ptr [edx+eax*4+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xe01b90
       jmp     mscorlib_ni+0xe01b81
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xe01c36
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       mov     ecx,8
       add     byte ptr [eax],al
       call    System.ThrowHelper.GetArgumentName(System.ExceptionArgument)
       mov     ebx,eax
       mov     ecx,4A49h
       dec     ecx
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jne     mscorlib_ni+0xe01c50
       adc     al,83h
       sti
       push    dword ptr [ecx-47h]
       push    cs
       add     byte ptr [eax],al
       add     byte ptr [ebp-2117F7AFh],cl
       rcl     cl,cl
       ???
       jmp     mscorlib_ni+0xe01c62
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xe01c62
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10c0f46
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xe064b0
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c0f18
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c0f6c
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10c0f90
       lea     ecx,[eax+eax*4]
       lea     edx,[edx+ecx*4+8]
       push    dword ptr [edx+10h]
       push    dword ptr [edx+0Ch]
       push    dword ptr [edx+8]
       push    dword ptr [edx+4]
       push    dword ptr [edx]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xe064b0
       jmp     mscorlib_ni+0xe064a1
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xe06566
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       mov     edx,8BFF51A5h
       fdivr   dword ptr [ecx+4A49h]
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xe06575
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xe06592
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xe06592
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xe06592
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10c186a
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xe0a560
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c183c
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c1890
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10c18b4
       lea     eax,[edx+eax*8+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xe0a560
       jmp     mscorlib_ni+0xe0a551
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xe0a60a
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       push    ss
       push    ecx
       dec     dword ptr [ebx+4A49B9D8h]
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xe0a619
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xe0a636
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xe0a636
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xe0a636
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10c2c22
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xe146e0
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c2bf4
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c2c48
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10c2c6c
       mov     edx,dword ptr [edx+eax*4+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xe146e0
       jmp     mscorlib_ni+0xe146d1
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xe14786
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       mov     ecx,8
       add     byte ptr [eax],al
       call    System.ThrowHelper.GetArgumentName(System.ExceptionArgument)
       mov     ebx,eax
       mov     ecx,4A49h
       dec     ecx
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jne     mscorlib_ni+0xe147a0
       adc     al,83h
       sti
       push    dword ptr [ecx-47h]
       push    cs
       add     byte ptr [eax],al
       add     byte ptr [ebp-7117F7AFh],cl
       cmps    dword ptr [esi],dword ptr es:[edi]
       sar     bh,1
       jmp     mscorlib_ni+0xe147b2
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xe147b2
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10c3172
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xe17900
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c3144
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c3198
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10c31bc
       push    dword ptr [edx+eax*4+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xe17900
       jmp     mscorlib_ni+0xe178f1
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xe179a6
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       mov     ecx,8
       add     byte ptr [eax],al
       call    System.ThrowHelper.GetArgumentName(System.ExceptionArgument)
       mov     ebx,eax
       mov     ecx,4A49h
       dec     ecx
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jne     mscorlib_ni+0xe179c0
       adc     al,83h
       sti
       push    dword ptr [ecx-47h]
       push    cs
       add     byte ptr [eax],al
       add     byte ptr System_ni+0x990851
       jne     mscorlib_ni+0xe1798d
       ???
       jmp     mscorlib_ni+0xe179d2
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xe179d2
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10c4966
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xe24060
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c4938
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c498c
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10c49b0
       mov     edx,dword ptr [edx+eax*4+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xe24060
       jmp     mscorlib_ni+0xe24051
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xe24106
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       mov     ecx,8
       add     byte ptr [eax],al
       call    System.ThrowHelper.GetArgumentName(System.ExceptionArgument)
       mov     ebx,eax
       mov     ecx,4A49h
       dec     ecx
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jne     mscorlib_ni+0xe24120
       adc     al,83h
       sti
       push    dword ptr [ecx-47h]
       push    cs
       add     byte ptr [eax],al
       add     byte ptr [ebp+0EE80851h],cl
       scas    byte ptr es:[edi]
       iretd
       ???
       jmp     mscorlib_ni+0xe24132
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xe24132
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10c4f72
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xe27090
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c4f44
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c4f98
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10c4fbc
       movzx   edx,word ptr [edx+eax*2+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xe27090
       jmp     mscorlib_ni+0xe27081
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xe27136
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       jmp     B9D8:8BFF4F99
       dec     ecx
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xe27145
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xe27162
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xe27162
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xe27162
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10c66de
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xe33e30
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c66b0
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c6704
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10c6728
       shl     eax,4
       lea     eax,[edx+eax+8]
       push    dword ptr [eax+0Ch]
       push    dword ptr [eax+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xe33e30
       jmp     mscorlib_ni+0xe33e21
       int     3
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xe33ee6
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       dec     esi
       dec     dword ptr [ebx+8B9F0h]
       or      byte ptr [eax],al
       add     byte ptr [eax],al
       call    System.ThrowHelper.GetArgumentName(System.ExceptionArgument)
       mov     ebx,eax
       fdivr   dword ptr [ecx+4A49h]
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       dec     esi
       inc     dword ptr msvcrt!modf+0x175f
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xe33f12
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xe33f12
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xe33f12
       mov     ecx,0Eh
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10c7e4a
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xe43000
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c7e1c
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c7e70
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10c7e94
       fld     qword ptr [edx+eax*8+8]
       sub     esp,8
       fstp    qword ptr [esp]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xe43000
       jmp     mscorlib_ni+0xe42ff1
       int     3
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xe430ae
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       dec     ebp
       dec     dword ptr [ebx+8B9F0h]
       or      byte ptr [eax],al
       add     byte ptr [eax],al
       call    System.ThrowHelper.GetArgumentName(System.ExceptionArgument)
       mov     ebx,eax
       fdivr   dword ptr [ecx+4A49h]
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       dec     ebp
       inc     dword ptr msvcrt!modf+0x175f
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xe430da
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xe430da
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xe430da
       mov     ecx,0Eh
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10c8312
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xe45d50
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c82e4
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c8338
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10c835c
       movzx   edx,byte ptr [edx+eax+8]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xe45d50
       jmp     mscorlib_ni+0xe45d41
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xe45df6
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       sub     ch,byte ptr [ebp-277400B3h]
       mov     ecx,4A49h
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
       jg      mscorlib_ni+0xe45e05
       add     byte ptr [ebp+14h],dh
       cmp     ebx,0FFFFFFFFh
       je      mscorlib_ni+0xe45e22
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       jmp     mscorlib_ni+0xe45e22
       cmp     ebx,dword ptr [edi+0Ch]
       jb      mscorlib_ni+0xe45e22
       mov     ecx,0Eh
       lea     edx,[ecx+8]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     esi,ecx
       mov     edi,edx
       test    edi,edi
       je      mscorlib_ni+0x10c8f46
       mov     ebx,dword ptr [esi+10h]
       xor     edx,edx
       mov     dword ptr [ebp-10h],edx
       cmp     dword ptr [esi+0Ch],0
       jg      mscorlib_ni+0xe4b8e0
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c8f18
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       cmp     ebx,dword ptr [esi+10h]
       jne     mscorlib_ni+0x10c8f6c
       mov     eax,dword ptr [ebp-10h]
       mov     edx,dword ptr [esi+4]
       cmp     eax,dword ptr [edx+4]
       jae     mscorlib_ni+0x10c8f90
       lea     eax,[edx+eax*8+8]
       push    dword ptr [eax+4]
       push    dword ptr [eax]
       mov     ecx,edi
       mov     eax,dword ptr [ecx+0Ch]
       mov     ecx,dword ptr [ecx+4]
       call    eax
       inc     dword ptr [ebp-10h]
       mov     eax,dword ptr [ebp-10h]
       cmp     eax,dword ptr [esi+0Ch]
       jl      mscorlib_ni+0xe4b8e0
       jmp     mscorlib_ni+0xe4b8d1
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     edi,ecx
       mov     ebx,edx
       mov     esi,dword ptr [ebp+0Ch]
       cmp     dword ptr [ebp+8],0
       jne     mscorlib_ni+0xe4b98a
       mov     ecx,offset mscorlib_ni+0x4f4674
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       lock    mov ecx,8
       add     al,ch
       xchg    eax,esi
       push    ecx
       dec     ebp
       dec     dword ptr [ebx+4A49B9D8h]
       dec     edx
       add     byte ptr [eax],al
       call    mscorlib_ni+0x381cfc
       mov     ecx,eax
       call    System.Environment.GetResourceFromDefault(System.String)
       mov     edi,eax
       mov     ecx,esi
       call    System.Exception.Init()
       lea     edx,[esi+10h]
       call    mscorlib_ni+0x31b040
       mov     dword ptr [esi+40h],80131501h
       lea     edx,[esi+50h]
       call    mscorlib_ni+0x31b0a0
       mov     dword ptr [esi+40h],80070057h
       mov     dword ptr [esi+40h],80004003h
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       cmp     dword ptr [edi+0Ch],0
; Total bytes of code 10883
```
```assembly
; foreach_perf.LangForEachVSLambForEach+<>c.<LambForEach>b__2_0(System.Text.StringBuilder)
                   stringField.ForEach(x => x.Clear());
                                     ^^^^^^^^^
       IL_0000: ldarg.1
       IL_0001: callvirt System.Text.StringBuilder System.Text.StringBuilder::Clear()
       IL_0006: pop
       cmp     byte ptr [edx],al
       mov     ecx,edx
       xor     edx,edx
       call    System.Text.StringBuilder.set_Length(Int32)
       IL_0007: ret
       ret
; Total bytes of code 12
```

## .NET Framework 4.7.2 (CLR 4.0.30319.42000), 32bit LegacyJIT-v4.7.3324.0
```assembly
; foreach_perf.LangForEachVSLambForEach.For()
                   for(int i = 0; i < stringField.Count; i++) {
                ^^^^^^^^^
       IL_0000: ldc.i4.0
       IL_0001: stloc.0
       IL_0002: br.s IL_001a
       xor     edi,edi
       jmp     M00_L02
                       stringField[i].Clear();
                ^^^^^^^^^^^^^^^^^^^^^^^
       IL_0004: ldarg.0
       IL_0005: ldfld System.Collections.Generic.List`1<System.Text.StringBuilder> foreach_perf.LangForEachVSLambForEach::stringField
       IL_000a: ldloc.0
       IL_000b: callvirt !0 System.Collections.Generic.List`1<System.Text.StringBuilder>::get_Item(System.Int32)
       IL_0010: callvirt System.Text.StringBuilder System.Text.StringBuilder::Clear()
       IL_0015: pop
M00_L00:
       cmp     edi,dword ptr [esi+0Ch]
       jb      M00_L01
       mov     ecx,0Dh
       lea     edx,[ecx+9]
       call    System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
M00_L01:
       mov     eax,dword ptr [esi+4]
       cmp     edi,dword ptr [eax+4]
       jae     04c33b84
       mov     ecx,dword ptr [eax+edi*4+8]
       cmp     byte ptr [ecx],al
       xor     edx,edx
       call    System.Text.StringBuilder.set_Length(Int32)
                   for(int i = 0; i < stringField.Count; i++) {
                                                  ^^^
       IL_0016: ldloc.0
       IL_0017: ldc.i4.1
       IL_0018: add
       IL_0019: stloc.0
       inc     edi
                   for(int i = 0; i < stringField.Count; i++) {
                           ^^^^^^^^^^^^^^^^^^^^^
       IL_001a: ldloc.0
       IL_001b: ldarg.0
       IL_001c: ldfld System.Collections.Generic.List`1<System.Text.StringBuilder> foreach_perf.LangForEachVSLambForEach::stringField
       IL_0021: callvirt System.Int32 System.Collections.Generic.List`1<System.Text.StringBuilder>::get_Count()
       IL_0026: blt.s IL_0004
       IL_0028: ldarg.0
       IL_0029: ldfld System.Collections.Generic.List`1<System.Text.StringBuilder> foreach_perf.LangForEachVSLambForEach::stringField
       IL_002e: callvirt System.Int32 System.Collections.Generic.List`1<System.Text.StringBuilder>::get_Count()
       IL_0033: ret
M00_L02:
       mov     esi,dword ptr [ebx+4]
       cmp     edi,dword ptr [esi+0Ch]
       jl      M00_L00
       mov     eax,dword ptr [esi+0Ch]
; Total bytes of code 55
```
```assembly
; System.ThrowHelper.ThrowArgumentOutOfRangeException(System.ExceptionArgument, System.ExceptionResource)
       IL_0018: ldarg.0
       call    System.ThrowHelper.GetArgumentName(System.ExceptionArgument)
       IL_0019: call System.String System.ThrowHelper::GetArgumentName(System.ExceptionArgument)
       IL_001e: ldarg.1
       mov     dword ptr [ebp-8],eax
       mov     ecx,esi
       IL_001f: call System.String System.ThrowHelper::GetResourceName(System.ExceptionResource)
       IL_0024: call System.String System.Environment::GetResourceString(System.String)
       call    System.ThrowHelper.GetResourceName(System.ExceptionResource)
       mov     dword ptr [ebp-0Ch],eax
       mov     ecx,offset mscorlib_ni+0x4f4760
       call    mscorlib_ni+0x31b008
       mov     esi,eax
       mov     ecx,dword ptr [ebp-0Ch]
       call    System.Environment.GetResourceFromDefault(System.String)
       push    eax
       mov     edx,dword ptr [ebp-8]
       mov     ecx,esi
       IL_0029: newobj System.Void System.ArgumentOutOfRangeException::.ctor(System.String,System.String)
       call    System.ArgumentOutOfRangeException..ctor(System.String, System.String)
       IL_002e: throw
       mov     ecx,esi
       call    mscorlib_ni+0x31b090
       int     3
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       sub     esp,8
       call    System.ThrowHelper.GetResourceName(System.ExceptionResource)
       mov     dword ptr [ebp-8],eax
       mov     ecx,offset mscorlib_ni+0x4f45c4
       call    mscorlib_ni+0x31b008
; Total bytes of code 83
```
```assembly
; System.Text.StringBuilder.set_Length(Int32)
       IL_0000: ldarg.1
       IL_0001: ldc.i4.0
       IL_0002: bge.s IL_0019
       IL_0004: ldstr "value"
       IL_0009: ldstr "ArgumentOutOfRange_NegativeLength"
       IL_000e: call System.String System.Environment::GetResourceString(System.String)
       test    edi,edi
       jl      mscorlib_ni+0x10278a0
       cmp     edi,dword ptr [esi+14h]
       jg      mscorlib_ni+0x10278da
       mov     eax,dword ptr [esi+4]
       mov     ecx,dword ptr [eax+4]
       add     ecx,dword ptr [esi+10h]
       IL_003e: ldarg.1
       IL_003f: brtrue.s IL_0058
       test    edi,edi
       jne     mscorlib_ni+0x3f6ddf
       IL_0041: ldarg.0
       IL_0042: ldfld System.Text.StringBuilder System.Text.StringBuilder::m_ChunkPrevious
       IL_0047: brtrue.s IL_0058
       cmp     dword ptr [esi+8],0
       jne     mscorlib_ni+0x3f6ddf
       IL_0049: ldarg.0
       IL_004a: ldc.i4.0
       IL_004b: stfld System.Int32 System.Text.StringBuilder::m_ChunkLength
       xor     edx,edx
       mov     dword ptr [esi+0Ch],edx
       IL_0050: ldarg.0
       IL_0051: ldc.i4.0
       IL_0052: stfld System.Int32 System.Text.StringBuilder::m_ChunkOffset
       mov     dword ptr [esi+10h],edx
       IL_0057: ret
       IL_0058: ldarg.1
       IL_0059: ldarg.0
       IL_005a: call System.Int32 System.Text.StringBuilder::get_Length()
       IL_005f: sub
       IL_0060: stloc.1
       lea     esp,[ebp-8]
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     eax,edi
       mov     edx,dword ptr [esi+10h]
       add     edx,dword ptr [esi+0Ch]
       sub     eax,edx
       IL_0061: ldloc.1
       IL_0062: ldc.i4.0
       IL_0063: ble.s IL_006f
       test    eax,eax
       jg      mscorlib_ni+0x3f6e66
       IL_006f: ldarg.0
       IL_0070: ldarg.1
       IL_0071: call System.Text.StringBuilder System.Text.StringBuilder::FindChunkForIndex(System.Int32)
       IL_0076: stloc.2
       mov     dword ptr [ebp-10h],esi
       cmp     dword ptr [esi+10h],edi
       jle     mscorlib_ni+0x3f6e06
       mov     eax,dword ptr [ebp-10h]
       mov     eax,dword ptr [eax+8]
       mov     dword ptr [ebp-10h],eax
       mov     eax,dword ptr [ebp-10h]
       cmp     dword ptr [eax+10h],edi
       jg      mscorlib_ni+0x3f6df5
       IL_0077: ldloc.2
       IL_0078: ldarg.0
       IL_0079: beq.s IL_00bf
       cmp     dword ptr [ebp-10h],esi
       je      mscorlib_ni+0x3f6e56
       IL_007b: ldloc.0
       IL_007c: ldloc.2
       IL_007d: ldfld System.Int32 System.Text.StringBuilder::m_ChunkOffset
       IL_0082: sub
       IL_0083: stloc.3
       mov     eax,dword ptr [ebp-10h]
       sub     ecx,dword ptr [eax+10h]
       mov     edx,ecx
       IL_0084: ldloc.3
       IL_0085: newarr System.Char
       IL_008a: stloc.s V_4
       mov     ecx,offset mscorlib_ni+0x1632
       call    mscorlib_ni+0x31b0c8
       mov     dword ptr [ebp-0Ch],eax
       IL_008c: ldloc.2
       IL_008d: ldfld System.Char[] System.Text.StringBuilder::m_ChunkChars
       IL_0092: ldloc.s V_4
       IL_0094: ldloc.2
       IL_0095: ldfld System.Int32 System.Text.StringBuilder::m_ChunkLength
       mov     eax,dword ptr [ebp-10h]
       mov     ecx,dword ptr [eax+4]
       mov     eax,dword ptr [ebp-10h]
       push    dword ptr [eax+0Ch]
       mov     edx,dword ptr [ebp-0Ch]
       IL_009a: call System.Void System.Array::Copy(System.Array,System.Array,System.Int32)
       call    System.Array.Copy(System.Array, System.Array, Int32)
       IL_009f: ldarg.0
       IL_00a0: ldloc.s V_4
       IL_00a2: stfld System.Char[] System.Text.StringBuilder::m_ChunkChars
       mov     eax,dword ptr [ebp-0Ch]
       lea     edx,[esi+4]
       call    mscorlib_ni+0x31b010
       IL_00a7: ldarg.0
       IL_00a8: ldloc.2
       IL_00a9: ldfld System.Text.StringBuilder System.Text.StringBuilder::m_ChunkPrevious
       IL_00ae: stfld System.Text.StringBuilder System.Text.StringBuilder::m_ChunkPrevious
       mov     eax,dword ptr [ebp-10h]
       mov     eax,dword ptr [eax+8]
       lea     edx,[esi+8]
       call    mscorlib_ni+0x31b010
       IL_00b3: ldarg.0
       IL_00b4: ldloc.2
       IL_00b5: ldfld System.Int32 System.Text.StringBuilder::m_ChunkOffset
       IL_00ba: stfld System.Int32 System.Text.StringBuilder::m_ChunkOffset
       mov     eax,dword ptr [ebp-10h]
       mov     eax,dword ptr [eax+10h]
       mov     dword ptr [esi+10h],eax
       IL_00bf: ldarg.0
       IL_00c0: ldarg.1
       IL_00c1: ldloc.2
       IL_00c2: ldfld System.Int32 System.Text.StringBuilder::m_ChunkOffset
       IL_00c7: sub
       IL_00c8: stfld System.Int32 System.Text.StringBuilder::m_ChunkLength
       mov     eax,dword ptr [ebp-10h]
       sub     edi,dword ptr [eax+10h]
       mov     dword ptr [esi+0Ch],edi
       IL_00cd: ret
       lea     esp,[ebp-8]
       pop     esi
       pop     edi
       pop     ebp
       ret
       IL_0065: ldarg.0
       IL_0066: ldc.i4.0
       IL_0067: ldloc.1
       push    eax
       mov     ecx,esi
       xor     edx,edx
       IL_0068: call System.Text.StringBuilder System.Text.StringBuilder::Append(System.Char,System.Int32)
       IL_006d: pop
       call    System.Text.StringBuilder.Append(Char, Int32)
       IL_006e: ret
       lea     esp,[ebp-8]
       pop     esi
       pop     edi
       pop     ebp
       ret
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       sub     esp,1Ch
       mov     esi,ecx
       lea     edi,[ebp-24h]
       mov     ecx,6
       xor     eax,eax
       rep     stos dword ptr es:[edi]
       mov     ecx,esi
       mov     esi,ecx
       mov     edi,edx
       mov     ecx,dword ptr [esi+30h]
       mov     eax,dword ptr [ecx]
       mov     eax,dword ptr [eax+34h]
       call    dword ptr [eax]
       mov     dword ptr [ebp-24h],eax
       xor     edx,edx
       mov     dword ptr [ebp-20h],edx
       IL_0013: newobj System.Void System.ArgumentOutOfRangeException::.ctor(System.String,System.String)
       loopne  mscorlib_ni+0x3f6e27
       jge     mscorlib_ni+0x3f6e89
       add     byte ptr [ebp+eax-18h],dh
       IL_0018: throw
       IL_0019: ldarg.1
       IL_001a: ldarg.0
       IL_001b: call System.Int32 System.Text.StringBuilder::get_MaxCapacity()
       IL_0020: ble.s IL_0037
       IL_0022: ldstr "value"
       IL_0027: ldstr "ArgumentOutOfRange_SmallCapacity"
       IL_002c: call System.String System.Environment::GetResourceString(System.String)
       je      mscorlib_ni+0x3f6eb1
       call    System.Threading.Monitor.ThrowLockTakenException()
       lea     edx,[ebp-20h]
       mov     ecx,dword ptr [ebp-24h]
       call    System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
       mov     ecx,dword ptr [esi+30h]
       push    dword ptr [ebp+8]
       mov     edx,edi
       mov     eax,dword ptr [ecx]
       mov     eax,dword ptr [eax+2Ch]
       call    dword ptr [eax+14h]
       mov     dword ptr [ebp-18h],0
       mov     dword ptr [ebp-14h],0FCh
       push    offset mscorlib_ni+0x3f6efd
       IL_0031: newobj System.Void System.ArgumentOutOfRangeException::.ctor(System.String,System.String)
       jmp     mscorlib_ni+0x3f6ee1
       movzx   eax,byte ptr [ebp-20h]
       IL_0036: throw
       IL_0037: ldarg.0
       IL_0038: call System.Int32 System.Text.StringBuilder::get_Capacity()
       IL_003d: stloc.0
       loopne  mscorlib_ni+0x3f6e6b
       sal     byte ptr [eax+ecx-75h],4Dh
       fsub    st(0),st
       outs    dx,dword ptr [esi]
       bnd     call fword ptr fs:[eax-1]
       loopne  mscorlib_ni+0x3f6e82
       clc
       pop     esi
       pop     edi
       pop     ebp
       ret     4
       mov     dword ptr [ebp-14h],0
; Total bytes of code 349
```
```assembly
; System.Text.StringBuilder.Clear()
       IL_0000: ldarg.0
       IL_0001: ldc.i4.0
       mov     ecx,esi
       xor     edx,edx
       IL_0002: call System.Void System.Text.StringBuilder::set_Length(System.Int32)
       call    System.Text.StringBuilder.set_Length(Int32)
       IL_0007: ldarg.0
       IL_0008: ret
       mov     eax,esi
; Total bytes of code 11
```

## .NET Framework 4.7.2 (CLR 4.0.30319.42000), 32bit LegacyJIT-v4.7.3324.0
```assembly
; foreach_perf.LangForEachVSLambForEach.LangForEach()
                   foreach (var item in stringField)
                                 ^^^^^^^^^^^
       IL_0000: ldarg.0
       IL_0001: ldfld System.Collections.Generic.List`1<System.Text.StringBuilder> foreach_perf.LangForEachVSLambForEach::stringField
       IL_0006: callvirt System.Collections.Generic.List`1/Enumerator<!0> System.Collections.Generic.List`1<System.Text.StringBuilder>::GetEnumerator()
       IL_000b: stloc.0
       IL_000c: br.s IL_001b
       IL_000e: ldloca.s V_0
       IL_0010: call !0 System.Collections.Generic.List`1/Enumerator<System.Text.StringBuilder>::get_Current()
       IL_0015: callvirt System.Text.StringBuilder System.Text.StringBuilder::Clear()
       IL_001a: pop
       mov     eax,dword ptr [ebp-40h]
       mov     edx,dword ptr [eax+4]
       cmp     byte ptr [edx],al
       lea     edi,[ebp-3Ch]
       xorps   xmm0,xmm0
       movq    mmword ptr [edi],xmm0
       movq    mmword ptr [edi+8],xmm0
       mov     dword ptr [ebp-3Ch],edx
       xor     ecx,ecx
       mov     dword ptr [ebp-34h],ecx
       mov     edx,dword ptr [edx+10h]
       mov     dword ptr [ebp-30h],edx
       mov     dword ptr [ebp-38h],ecx
       lea     edi,[ebp-2Ch]
       lea     esi,[ebp-3Ch]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
                   foreach (var item in stringField)
                              ^^
       IL_001b: ldloca.s V_0
       lea     ecx,[ebp-2Ch]
       mov     edx,0C15778h
       call    System.Collections.Generic.List`1+Enumerator[[System.__Canon, mscorlib]].MoveNext()
       test    eax,eax
       je      M00_L01
M00_L00:
       mov     ecx,dword ptr [ebp-28h]
       cmp     byte ptr [ecx],al
       xor     edx,edx
       call    System.Text.StringBuilder.set_Length(Int32)
       lea     ecx,[ebp-2Ch]
       mov     edx,0C15778h
       IL_001d: call System.Boolean System.Collections.Generic.List`1/Enumerator<System.Text.StringBuilder>::MoveNext()
       IL_0022: brtrue.s IL_000e
       IL_0024: leave.s IL_0034
       IL_0026: ldloca.s V_0
       IL_0028: constrained. System.Collections.Generic.List`1/Enumerator<System.Text.StringBuilder>
       IL_002e: callvirt System.Void System.IDisposable::Dispose()
       call    System.Collections.Generic.List`1+Enumerator[[System.__Canon, mscorlib]].MoveNext()
       test    eax,eax
       jne     M00_L00
M00_L01:
       mov     dword ptr [ebp-18h],0
       mov     dword ptr [ebp-14h],0FCh
       push    4FF3BE3h
       jmp     M00_L02
                   return stringField.Count;
            ^^^^^^^^^^^^^^^^^^^^^^^^^
       IL_0033: endfinally
M00_L02:
       pop     eax
       jmp     eax
       IL_0034: ldarg.0
       IL_0035: ldfld System.Collections.Generic.List`1<System.Text.StringBuilder> foreach_perf.LangForEachVSLambForEach::stringField
       IL_003a: callvirt System.Int32 System.Collections.Generic.List`1<System.Text.StringBuilder>::get_Count()
       IL_003f: ret
       mov     eax,dword ptr [ebp-40h]
       mov     eax,dword ptr [eax+4]
       mov     eax,dword ptr [eax+0Ch]
; Total bytes of code 129
```
```assembly
; System.Collections.Generic.List`1+Enumerator[[System.__Canon, mscorlib]].MoveNext()
       IL_0000: ldarg.0
       IL_0001: ldfld System.Collections.Generic.List`1<T> System.Collections.Generic.List`1/Enumerator<T>::list
       IL_0006: stloc.0
       mov     ecx,dword ptr [edx]
       IL_0007: ldarg.0
       IL_0008: ldfld System.Int32 System.Collections.Generic.List`1/Enumerator<T>::version
       IL_000d: ldloc.0
       IL_000e: ldfld System.Int32 System.Collections.Generic.List`1<T>::_version
       IL_0013: bne.un.s IL_004a
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     M01_L00
       IL_0015: ldarg.0
       IL_0016: ldfld System.Int32 System.Collections.Generic.List`1/Enumerator<T>::index
       IL_001b: ldloc.0
       IL_001c: ldfld System.Int32 System.Collections.Generic.List`1<T>::_size
       IL_0021: bge.un.s IL_004a
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     M01_L00
       IL_0023: ldarg.0
       IL_0024: ldloc.0
       IL_0025: ldfld T[] System.Collections.Generic.List`1<T>::_items
       IL_002a: ldarg.0
       IL_002b: ldfld System.Int32 System.Collections.Generic.List`1/Enumerator<T>::index
       IL_0030: ldelem.any T
       IL_0035: stfld T System.Collections.Generic.List`1/Enumerator<T>::current
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     M01_L01
       lea     ecx,[ebx+ebx*8]
       lea     esi,[eax+ecx*4+8]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       call    clr+0xde08
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       IL_003a: ldarg.0
       IL_003b: ldarg.0
       IL_003c: ldfld System.Int32 System.Collections.Generic.List`1/Enumerator<T>::index
       IL_0041: ldc.i4.1
       IL_0042: add
       IL_0043: stfld System.Int32 System.Collections.Generic.List`1/Enumerator<T>::index
       inc     dword ptr [edx+4]
       IL_0048: ldc.i4.1
       IL_0049: ret
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
M01_L00:
       mov     ecx,edx
       call    dword ptr ds:[2B2DEE4h]
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
M01_L01:
       call    clr!CreateHistoryReader+0x98380
       int     3
       add     byte ptr [eax],al
       add     byte ptr [eax],al
       add     byte ptr [eax],al
       add     byte ptr [eax-34h],dl
       mov     bl,2
       add     byte ptr [eax],al
       add     byte ptr [eax],al
       dec     eax
       int     3
       mov     bl,2
       clc
       fnsave  [edx-74A9A8FEh]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       mov     edx,ecx
       mov     ecx,dword ptr [edx]
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     System_Core_ni+0x50cd68
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     System_Core_ni+0x50cd68
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     System_Core_ni+0x50cd74
       lea     ecx,[ebx+ebx*2]
       lea     esi,[eax+ecx*4+8]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [edx+4]
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,edx
       call    System.Collections.Generic.List`1+Enumerator[[System.Security.Cryptography.NCryptNative+NCryptBuffer, System.Core]].MoveNextRare()
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    System_Core_ni+0x19de20
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,edx
       lea     edx,[esi]
       call    System_Core_ni+0x19de30
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       mov     edx,ecx
       mov     ecx,dword ptr [edx]
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     System_Core_ni+0x51ec7e
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     System_Core_ni+0x51ec7e
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     System_Core_ni+0x51ec8a
       lea     ecx,[ebx+ebx*4]
       lea     esi,[eax+ecx*4+8]
       call    System_Core_ni+0x19de70
       call    System_Core_ni+0x19de70
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [edx+4]
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,edx
       call    System.Collections.Generic.List`1+Enumerator[[System.Security.Cryptography.CngProperty, System.Core]].MoveNextRare()
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    System_Core_ni+0x19de20
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,edx
       lea     edx,[esi]
       call    System_Core_ni+0x19de30
       xor     edx,edx
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     dword ptr [ebp-10h],edx
       mov     ebx,ecx
       mov     ecx,dword ptr [ebx]
       mov     eax,dword ptr [ebx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     System_Core_ni+0x565a55
       mov     esi,dword ptr [ebx+4]
       cmp     esi,dword ptr [ecx+0Ch]
       jae     System_Core_ni+0x565a55
       lea     edi,[ebx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     esi,dword ptr [eax+4]
       jae     System_Core_ni+0x565a62
       lea     esi,[eax+esi*8+8]
       call    System_Core_ni+0x19de70
       call    System_Core_ni+0x19de70
       inc     dword ptr [ebx+4]
       mov     eax,1
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,ebx
       call    System.Collections.Generic.List`1+Enumerator[[System.Linq.Parallel.Pair`2[[System.__Canon, mscorlib],[System.__Canon, mscorlib]], System.Core]].MoveNextRare()
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    System_Core_ni+0x19de20
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,edx
       lea     edx,[esi]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     dword ptr [ebp-10h],edx
       mov     ebx,ecx
       mov     ecx,dword ptr [ebx]
       mov     eax,dword ptr [ebx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     System_Core_ni+0x57c3ad
       mov     esi,dword ptr [ebx+4]
       cmp     esi,dword ptr [ecx+0Ch]
       jae     System_Core_ni+0x57c3ad
       lea     edi,[ebx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     esi,dword ptr [eax+4]
       jae     System_Core_ni+0x57c3ba
       lea     esi,[eax+esi*8+8]
       call    System_Core_ni+0x19de70
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [ebx+4]
       mov     eax,1
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,ebx
       call    System.Collections.Generic.List`1+Enumerator[[System.Linq.Parallel.Pair`2[[System.__Canon, mscorlib],[System.Int32, mscorlib]], System.Core]].MoveNextRare()
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    System_Core_ni+0x19de20
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,edx
       lea     edx,[esi]
       call    System_Core_ni+0x19de30
       xor     edx,edx
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     edx,dword ptr [ecx]
       mov     eax,dword ptr [ecx+8]
       cmp     eax,dword ptr [edx+10h]
       jne     System_ni+0x760fa1
       mov     esi,dword ptr [ecx+4]
       cmp     esi,dword ptr [edx+0Ch]
       jae     System_ni+0x760fa1
       mov     eax,dword ptr [edx+4]
       cmp     esi,dword ptr [eax+4]
       jae     System_ni+0x760fa9
       mov     eax,dword ptr [eax+esi*4+8]
       mov     dword ptr [ecx+0Ch],eax
       inc     dword ptr [ecx+4]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.Text.RegularExpressions.RegexOptions, System]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    System_ni+0x149310
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       mov     eax,edx
       lea     edx,[ecx]
       call    System_ni+0x149330
       xor     edx,edx
       mov     dword ptr [ecx+4],edx
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       mov     edx,ecx
       mov     ecx,dword ptr [edx]
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     System_ni+0x773714
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     System_ni+0x773714
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     System_ni+0x773720
       lea     esi,[eax+ebx*8+8]
       call    System_ni+0x149358
       call    System_ni+0x149358
       inc     dword ptr [edx+4]
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,edx
       call    System.Collections.Generic.List`1+Enumerator[[System.Net.ConnectionReturnResult+RequestContext, System]].MoveNextRare()
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    System_ni+0x149310
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,edx
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    eax
       mov     dword ptr [ebp-0Ch],edx
       mov     edi,dword ptr [ecx]
       mov     eax,dword ptr [ecx+0Ch]
       cmp     eax,dword ptr [edi+10h]
       jne     mscorlib_ni+0x39bd7c
       mov     esi,dword ptr [ecx+8]
       cmp     esi,dword ptr [edi+0Ch]
       jae     mscorlib_ni+0x39bd7c
       mov     eax,dword ptr [edi+4]
       cmp     esi,dword ptr [eax+4]
       jae     mscorlib_ni+0x39bd86
       mov     eax,dword ptr [eax+esi*4+8]
       lea     edx,[ecx+4]
       call    mscorlib_ni+0x31b068
       inc     dword ptr [ecx+8]
       mov     eax,1
       pop     ecx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.__Canon, mscorlib]].MoveNextRare()
       pop     ecx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       push    esi
       nop
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,dword ptr [esi+0Ch]
       mov     edx,dword ptr [esi]
       cmp     eax,dword ptr [edx+10h]
       jne     mscorlib_ni+0x1000e54
       mov     eax,dword ptr [esi]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     dword ptr [ebp-10h],edx
       mov     ebx,ecx
       mov     esi,edx
       mov     ecx,dword ptr [ebx]
       mov     eax,dword ptr [ebx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0x3b63e7
       mov     edx,dword ptr [ebx+4]
       cmp     edx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0x3b63e7
       lea     edi,[ebx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0x3b63f6
       lea     esi,[eax+edx*8+8]
       call    mscorlib_ni+0x31b160
       call    mscorlib_ni+0x31b160
       inc     dword ptr [ebx+4]
       mov     eax,1
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,ebx
       mov     edx,esi
       call    System.Collections.Generic.List`1+Enumerator[[System.Collections.Generic.KeyValuePair`2[[System.__Canon, mscorlib],[System.__Canon, mscorlib]], mscorlib]].MoveNextRare()
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,dword ptr [esi+8]
       mov     edx,dword ptr [esi]
       cmp     eax,dword ptr [edx+10h]
       jne     mscorlib_ni+0x100e5d4
       mov     eax,dword ptr [esi]
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     esi,dword ptr [ecx]
       mov     eax,dword ptr [ecx+8]
       cmp     eax,dword ptr [esi+10h]
       jne     mscorlib_ni+0x3bccf2
       mov     edx,dword ptr [ecx+4]
       cmp     edx,dword ptr [esi+0Ch]
       jae     mscorlib_ni+0x3bccf2
       mov     eax,dword ptr [esi+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0x3bccfa
       movzx   eax,byte ptr [eax+edx+8]
       mov     byte ptr [ecx+0Ch],al
       inc     dword ptr [ecx+4]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.Byte, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       push    esi
       nop
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,dword ptr [esi+8]
       mov     edx,dword ptr [esi]
       cmp     eax,dword ptr [edx+10h]
       jne     mscorlib_ni+0x1011cb4
       mov     eax,dword ptr [esi]
       mov     eax,dword ptr [eax+0Ch]
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     esi,dword ptr [ecx]
       mov     eax,dword ptr [ecx+8]
       cmp     eax,dword ptr [esi+10h]
       jne     mscorlib_ni+0x3d2f73
       mov     edx,dword ptr [ecx+4]
       cmp     edx,dword ptr [esi+0Ch]
       jae     mscorlib_ni+0x3d2f73
       mov     eax,dword ptr [esi+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0x3d2f7b
       movzx   eax,word ptr [eax+edx*2+8]
       mov     word ptr [ecx+0Ch],ax
       inc     dword ptr [ecx+4]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.Char, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       movzx   eax,word ptr [ecx+0Ch]
       ret
       int     3
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     esi,dword ptr [ecx]
       mov     eax,dword ptr [ecx+8]
       cmp     eax,dword ptr [esi+10h]
       jne     mscorlib_ni+0x43dd31
       mov     edx,dword ptr [ecx+4]
       cmp     edx,dword ptr [esi+0Ch]
       jae     mscorlib_ni+0x43dd31
       mov     eax,dword ptr [esi+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0x43dd39
       mov     eax,dword ptr [eax+edx*4+8]
       mov     dword ptr [ecx+0Ch],eax
       inc     dword ptr [ecx+4]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.Int32, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       push    esi
       nop
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,dword ptr [esi+8]
       mov     edx,dword ptr [esi]
       cmp     eax,dword ptr [edx+10h]
       jne     mscorlib_ni+0x1046b88
       mov     eax,dword ptr [esi]
       mov     eax,dword ptr [eax+0Ch]
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     esi,dword ptr [ecx+8]
       mov     eax,dword ptr [ecx+10h]
       cmp     eax,dword ptr [esi+10h]
       jne     mscorlib_ni+0x450f51
       mov     edx,dword ptr [ecx+0Ch]
       cmp     edx,dword ptr [esi+0Ch]
       jae     mscorlib_ni+0x450f51
       mov     eax,dword ptr [esi+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0x450f59
       fld     qword ptr [eax+edx*8+8]
       fstp    qword ptr [ecx]
       inc     dword ptr [ecx+0Ch]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.Double, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       fld     qword ptr [ecx]
       ret
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,dword ptr [esi+10h]
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     edx,dword ptr [ecx+8]
       mov     eax,dword ptr [ecx+10h]
       cmp     eax,dword ptr [edx+10h]
       jne     mscorlib_ni+0x451e38
       mov     esi,dword ptr [ecx+0Ch]
       cmp     esi,dword ptr [edx+0Ch]
       jae     mscorlib_ni+0x451e38
       mov     eax,dword ptr [edx+4]
       cmp     esi,dword ptr [eax+4]
       jae     mscorlib_ni+0x451e40
       mov     edx,dword ptr [eax+esi*8+0Ch]
       mov     eax,dword ptr [eax+esi*8+8]
       mov     dword ptr [ecx],eax
       mov     dword ptr [ecx+4],edx
       inc     dword ptr [ecx+0Ch]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.Int64, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       mov     eax,dword ptr [ecx]
       mov     edx,dword ptr [ecx+4]
       ret
       int     3
       int     3
       int     3
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     esi,dword ptr [ecx]
       mov     eax,dword ptr [ecx+8]
       cmp     eax,dword ptr [esi+10h]
       jne     mscorlib_ni+0x453971
       mov     edx,dword ptr [ecx+4]
       cmp     edx,dword ptr [esi+0Ch]
       jae     mscorlib_ni+0x453971
       mov     eax,dword ptr [esi+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0x453979
       mov     eax,dword ptr [eax+edx*4+8]
       mov     dword ptr [ecx+0Ch],eax
       inc     dword ptr [ecx+4]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.UInt32, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       push    esi
       nop
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,dword ptr [esi+8]
       mov     edx,dword ptr [esi]
       cmp     eax,dword ptr [edx+10h]
       jne     mscorlib_ni+0x104c7d0
       mov     eax,dword ptr [esi]
       mov     eax,dword ptr [eax+0Ch]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     dword ptr [ebp-10h],edx
       mov     ebx,ecx
       mov     esi,edx
       mov     ecx,dword ptr [ebx]
       mov     eax,dword ptr [ebx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0x453a03
       mov     edx,dword ptr [ebx+4]
       cmp     edx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0x453a03
       lea     edi,[ebx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0x453a12
       lea     esi,[eax+edx*8+8]
       call    mscorlib_ni+0x31b160
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [ebx+4]
       mov     eax,1
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,ebx
       mov     edx,esi
       call    System.Collections.Generic.List`1+Enumerator[[System.Collections.Generic.KeyValuePair`2[[System.UInt32, mscorlib],[System.__Canon, mscorlib]], mscorlib]].MoveNextRare()
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     edi,edx
       add     ecx,0Ch
       mov     esi,ecx
       call    mscorlib_ni+0x31b160
       movs    dword ptr es:[edi],dword ptr [esi]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       mov     edx,ecx
       mov     ecx,dword ptr [edx]
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0x4643cd
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0x4643cd
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     mscorlib_ni+0x4643d9
       shl     ebx,4
       lea     esi,[eax+ebx+8]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [edx+4]
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,edx
       call    System.Collections.Generic.List`1+Enumerator[[System.Guid, mscorlib]].MoveNextRare()
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     edi,edx
       add     ecx,0Ch
       mov     esi,ecx
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       pop     esi
       pop     edi
       ret
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       mov     edx,ecx
       mov     ecx,dword ptr [edx]
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0x465570
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0x465570
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     mscorlib_ni+0x46557c
       lea     ecx,[ebx+ebx*2]
       lea     esi,[eax+ecx*4+8]
       call    mscorlib_ni+0x31b160
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [edx+4]
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,edx
       call    System.Collections.Generic.List`1+Enumerator[[System.ArraySegment`1[[System.Byte, mscorlib]], mscorlib]].MoveNextRare()
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     edi,edx
       add     ecx,0Ch
       mov     esi,ecx
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     dword ptr [ebp-10h],edx
       mov     ebx,ecx
       mov     esi,edx
       mov     ecx,dword ptr [ebx]
       mov     eax,dword ptr [ebx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0x465a99
       mov     edx,dword ptr [ebx+4]
       cmp     edx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0x465a99
       lea     edi,[ebx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0x465aa8
       lea     edx,[edx+edx*4]
       lea     esi,[eax+edx*4+8]
       call    mscorlib_ni+0x31b160
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [ebx+4]
       mov     eax,1
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,ebx
       mov     edx,esi
       call    System.Collections.Generic.List`1+Enumerator[[System.Collections.Generic.KeyValuePair`2[[System.Guid, mscorlib],[System.__Canon, mscorlib]], mscorlib]].MoveNextRare()
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,dword ptr [esi+8]
       mov     edx,dword ptr [esi]
       cmp     eax,dword ptr [edx+10h]
       jne     mscorlib_ni+0x10500ac
       mov     eax,dword ptr [esi]
       mov     eax,dword ptr [eax+0Ch]
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     esi,dword ptr [ecx]
       mov     eax,dword ptr [ecx+8]
       cmp     eax,dword ptr [esi+10h]
       jne     mscorlib_ni+0x467931
       mov     edx,dword ptr [ecx+4]
       cmp     edx,dword ptr [esi+0Ch]
       jae     mscorlib_ni+0x467931
       mov     eax,dword ptr [esi+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0x467939
       mov     eax,dword ptr [eax+edx*4+8]
       mov     dword ptr [ecx+0Ch],eax
       inc     dword ptr [ecx+4]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.Runtime.InteropServices.GCHandle, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       push    esi
       nop
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,dword ptr [esi+8]
       mov     edx,dword ptr [esi]
       cmp     eax,dword ptr [edx+10h]
       jne     mscorlib_ni+0x1050984
       mov     eax,dword ptr [esi]
       mov     eax,dword ptr [eax+0Ch]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     dword ptr [ebp-10h],edx
       mov     ebx,ecx
       mov     esi,edx
       mov     ecx,dword ptr [ebx]
       mov     eax,dword ptr [ebx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0x46a933
       mov     edx,dword ptr [ebx+4]
       cmp     edx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0x46a933
       lea     edi,[ebx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0x46a942
       lea     esi,[eax+edx*8+8]
       call    mscorlib_ni+0x31b160
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [ebx+4]
       mov     eax,1
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,ebx
       mov     edx,esi
       call    System.Collections.Generic.List`1+Enumerator[[System.Collections.Generic.KeyValuePair`2[[System.__Canon, mscorlib],[System.Int32, mscorlib]], mscorlib]].MoveNextRare()
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,dword ptr [esi+8]
       mov     edx,dword ptr [esi]
       cmp     eax,dword ptr [edx+10h]
       jne     mscorlib_ni+0x1051ac8
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       mov     edx,ecx
       mov     ecx,dword ptr [edx]
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0xb948f8
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0xb948f8
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     mscorlib_ni+0xb94904
       lea     esi,[eax+ebx*8+8]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [edx+4]
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       IL_004a: ldarg.0
       mov     ecx,edx
       IL_004b: call System.Boolean System.Collections.Generic.List`1/Enumerator<T>::MoveNextRare()
       IL_0050: ret
       call    System.Collections.Generic.List`1+Enumerator[[System.Runtime.InteropServices.WindowsRuntime.EventRegistrationToken, mscorlib]].MoveNextRare()
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,edx
       lea     edx,[esi]
       call    mscorlib_ni+0x31b068
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       mov     edx,ecx
       mov     ecx,dword ptr [edx]
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0xbf7920
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0xbf7920
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     mscorlib_ni+0xbf792c
       lea     esi,[eax+ebx*8+8]
       call    mscorlib_ni+0x31b160
       call    mscorlib_ni+0x31b160
       inc     dword ptr [edx+4]
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,edx
       call    System.Collections.Generic.List`1+Enumerator[[System.Collections.DictionaryEntry, mscorlib]].MoveNextRare()
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     dword ptr [ebp-10h],edx
       mov     ebx,ecx
       mov     esi,edx
       mov     ecx,dword ptr [ebx]
       mov     eax,dword ptr [ebx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0xc45693
       mov     edx,dword ptr [ebx+4]
       cmp     edx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0xc45693
       lea     edi,[ebx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0xc456a2
       lea     esi,[eax+edx*8+8]
       call    mscorlib_ni+0x31b160
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [ebx+4]
       mov     eax,1
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,ebx
       mov     edx,esi
       call    System.Collections.Generic.List`1+Enumerator[[System.Collections.Generic.KeyValuePair`2[[System.Int32, mscorlib],[System.__Canon, mscorlib]], mscorlib]].MoveNextRare()
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,edx
       lea     edx,[esi]
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     edx,dword ptr [ecx+8]
       mov     eax,dword ptr [ecx+10h]
       cmp     eax,dword ptr [edx+10h]
       jne     mscorlib_ni+0xc46f18
       mov     esi,dword ptr [ecx+0Ch]
       cmp     esi,dword ptr [edx+0Ch]
       jae     mscorlib_ni+0xc46f18
       mov     eax,dword ptr [edx+4]
       cmp     esi,dword ptr [eax+4]
       jae     mscorlib_ni+0xc46f20
       mov     edx,dword ptr [eax+esi*8+0Ch]
       mov     eax,dword ptr [eax+esi*8+8]
       mov     dword ptr [ecx],eax
       mov     dword ptr [ecx+4],edx
       inc     dword ptr [ecx+0Ch]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.UInt64, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,edx
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       mov     edx,ecx
       mov     ecx,dword ptr [edx]
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0xd0b990
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0xd0b990
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     mscorlib_ni+0xd0b99c
       imul    ecx,ebx,1Ch
       lea     esi,[eax+ecx+8]
       mov     ecx,7
       rep     movs dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [edx+4]
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,edx
       call    System.Collections.Generic.List`1+Enumerator[[System.Reflection.Emit.ExceptionHandler, mscorlib]].MoveNextRare()
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       mov     edx,ecx
       mov     ecx,dword ptr [edx]
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0xd546d8
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0xd546d8
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     mscorlib_ni+0xd546e4
       lea     esi,[eax+ebx*8+8]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [edx+4]
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,edx
       call    System.Collections.Generic.List`1+Enumerator[[System.TimeSpan, mscorlib]].MoveNextRare()
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,edx
       lea     edx,[esi]
       call    mscorlib_ni+0x31b068
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     esi,dword ptr [ecx]
       mov     eax,dword ptr [ecx+8]
       cmp     eax,dword ptr [esi+10h]
       jne     mscorlib_ni+0xd58073
       mov     edx,dword ptr [ecx+4]
       cmp     edx,dword ptr [esi+0Ch]
       jae     mscorlib_ni+0xd58073
       mov     eax,dword ptr [esi+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0xd5807b
       movsx   eax,word ptr [eax+edx*2+8]
       mov     word ptr [ecx+0Ch],ax
       inc     dword ptr [ecx+4]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.Int16, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       nop
       nop
       nop
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       mov     edx,ecx
       mov     ecx,dword ptr [edx]
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0xd64398
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0xd64398
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     mscorlib_ni+0xd643a4
       lea     esi,[eax+ebx*8+8]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [edx+4]
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,edx
       call    System.Collections.Generic.List`1+Enumerator[[System.Diagnostics.Tracing.EventProvider+SessionInfo, mscorlib]].MoveNextRare()
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,edx
       lea     edx,[esi]
       call    mscorlib_ni+0x31b068
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     esi,dword ptr [ecx]
       mov     eax,dword ptr [ecx+8]
       cmp     eax,dword ptr [esi+10h]
       jne     mscorlib_ni+0xd66e72
       mov     edx,dword ptr [ecx+4]
       cmp     edx,dword ptr [esi+0Ch]
       jae     mscorlib_ni+0xd66e72
       mov     eax,dword ptr [esi+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0xd66e7a
       movzx   eax,byte ptr [eax+edx+8]
       mov     byte ptr [ecx+0Ch],al
       inc     dword ptr [ecx+4]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.Threading.Tasks.ConcurrentExclusiveSchedulerPair+ProcessingMode, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       mov     eax,edx
       lea     edx,[ecx]
       call    mscorlib_ni+0x31b068
       xor     edx,edx
       mov     dword ptr [ecx+4],edx
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       mov     edx,ecx
       mov     ecx,dword ptr [edx]
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0xd7e950
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0xd7e950
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     mscorlib_ni+0xd7e95c
       lea     esi,[eax+ebx*8+8]
       call    mscorlib_ni+0x31b160
       call    mscorlib_ni+0x31b160
       inc     dword ptr [edx+4]
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,edx
       call    System.Collections.Generic.List`1+Enumerator[[System.Reflection.Emit.MethodBuilder+SymCustomAttr, mscorlib]].MoveNextRare()
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     esi,dword ptr [ecx]
       mov     eax,dword ptr [ecx+8]
       cmp     eax,dword ptr [esi+10h]
       jne     mscorlib_ni+0xd94cc3
       mov     edx,dword ptr [ecx+4]
       cmp     edx,dword ptr [esi+0Ch]
       jae     mscorlib_ni+0xd94cc3
       mov     eax,dword ptr [esi+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0xd94ccb
       movzx   eax,word ptr [eax+edx*2+8]
       mov     word ptr [ecx+0Ch],ax
       inc     dword ptr [ecx+4]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.UInt16, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       nop
       nop
       nop
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       mov     edx,ecx
       mov     ecx,dword ptr [edx]
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0xda5e50
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0xda5e50
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     mscorlib_ni+0xda5e5c
       lea     ecx,[ebx+ebx*4]
       lea     esi,[eax+ecx*4+8]
       mov     ecx,5
       rep     movs dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [edx+4]
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,edx
       call    System.Collections.Generic.List`1+Enumerator[[System.Collections.Generic.KeyValuePair`2[[System.Guid, mscorlib],[System.Int32, mscorlib]], mscorlib]].MoveNextRare()
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       mov     edx,ecx
       mov     ecx,dword ptr [edx]
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0xdbeaf8
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0xdbeaf8
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     mscorlib_ni+0xdbeb04
       lea     esi,[eax+ebx*8+8]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [edx+4]
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,edx
       call    System.Collections.Generic.List`1+Enumerator[[System.DateTime, mscorlib]].MoveNextRare()
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,edx
       lea     edx,[esi]
       call    mscorlib_ni+0x31b068
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     esi,dword ptr [ecx]
       mov     eax,dword ptr [ecx+8]
       cmp     eax,dword ptr [esi+10h]
       jne     mscorlib_ni+0xdbf321
       mov     edx,dword ptr [ecx+4]
       cmp     edx,dword ptr [esi+0Ch]
       jae     mscorlib_ni+0xdbf321
       mov     eax,dword ptr [esi+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0xdbf329
       fld     dword ptr [eax+edx*4+8]
       fstp    dword ptr [ecx+0Ch]
       inc     dword ptr [ecx+4]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.Single, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       mov     eax,edx
       lea     edx,[ecx]
       call    mscorlib_ni+0x31b068
       xor     edx,edx
       mov     dword ptr [ecx+4],edx
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     esi,dword ptr [ecx]
       mov     eax,dword ptr [ecx+8]
       cmp     eax,dword ptr [esi+10h]
       jne     mscorlib_ni+0xdca4f2
       mov     edx,dword ptr [ecx+4]
       cmp     edx,dword ptr [esi+0Ch]
       jae     mscorlib_ni+0xdca4f2
       mov     eax,dword ptr [esi+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0xdca4fa
       movsx   eax,byte ptr [eax+edx+8]
       mov     byte ptr [ecx+0Ch],al
       inc     dword ptr [ecx+4]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.SByte, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       mov     eax,edx
       lea     edx,[ecx]
       call    mscorlib_ni+0x31b068
       xor     edx,edx
       mov     dword ptr [ecx+4],edx
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       mov     edx,ecx
       mov     ecx,dword ptr [edx]
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0xdddc6c
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0xdddc6c
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     mscorlib_ni+0xdddc78
       lea     ecx,[ebx+ebx*2]
       lea     esi,[eax+ecx*4+8]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [edx+4]
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,edx
       call    System.Collections.Generic.List`1+Enumerator[[System.DateTimeOffset, mscorlib]].MoveNextRare()
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,edx
       lea     edx,[esi]
       call    mscorlib_ni+0x31b068
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       mov     edx,ecx
       mov     ecx,dword ptr [edx]
       mov     eax,dword ptr [edx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0xdfe7ad
       mov     ebx,dword ptr [edx+4]
       cmp     ebx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0xdfe7ad
       lea     edi,[edx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     ebx,dword ptr [eax+4]
       jae     mscorlib_ni+0xdfe7b9
       shl     ebx,4
       lea     esi,[eax+ebx+8]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [edx+4]
       mov     eax,1
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,edx
       call    System.Collections.Generic.List`1+Enumerator[[System.Decimal, mscorlib]].MoveNextRare()
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,edx
       lea     edx,[esi]
       call    mscorlib_ni+0x31b068
       xor     edx,edx
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     esi,dword ptr [ecx]
       mov     eax,dword ptr [ecx+8]
       cmp     eax,dword ptr [esi+10h]
       jne     mscorlib_ni+0xe02ee1
       mov     edx,dword ptr [ecx+4]
       cmp     edx,dword ptr [esi+0Ch]
       jae     mscorlib_ni+0xe02ee1
       mov     eax,dword ptr [esi+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0xe02ee9
       mov     eax,dword ptr [eax+edx*4+8]
       mov     dword ptr [ecx+0Ch],eax
       inc     dword ptr [ecx+4]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.IntPtr, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       mov     eax,edx
       lea     edx,[ecx]
       call    mscorlib_ni+0x31b068
       xor     edx,edx
       mov     dword ptr [ecx+4],edx
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     esi,dword ptr [ecx]
       mov     eax,dword ptr [ecx+8]
       cmp     eax,dword ptr [esi+10h]
       jne     mscorlib_ni+0xe252c1
       mov     edx,dword ptr [ecx+4]
       cmp     edx,dword ptr [esi+0Ch]
       jae     mscorlib_ni+0xe252c1
       mov     eax,dword ptr [esi+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0xe252c9
       mov     eax,dword ptr [eax+edx*4+8]
       mov     dword ptr [ecx+0Ch],eax
       inc     dword ptr [ecx+4]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.Reflection.Emit.Label, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       mov     eax,edx
       lea     edx,[ecx]
       call    mscorlib_ni+0x31b068
       xor     edx,edx
       mov     dword ptr [ecx+4],edx
       push    ebp
       mov     ebp,esp
       push    esi
       nop
       mov     esi,dword ptr [ecx]
       mov     eax,dword ptr [ecx+8]
       cmp     eax,dword ptr [esi+10h]
       jne     mscorlib_ni+0xe37562
       mov     edx,dword ptr [ecx+4]
       cmp     edx,dword ptr [esi+0Ch]
       jae     mscorlib_ni+0xe37562
       mov     eax,dword ptr [esi+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0xe3756a
       movzx   eax,byte ptr [eax+edx+8]
       mov     byte ptr [ecx+0Ch],al
       inc     dword ptr [ecx+4]
       mov     eax,1
       pop     esi
       pop     ebp
       ret
       call    System.Collections.Generic.List`1+Enumerator[[System.Boolean, mscorlib]].MoveNextRare()
       pop     esi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       mov     eax,edx
       lea     edx,[ecx]
       call    mscorlib_ni+0x31b068
       xor     edx,edx
       mov     dword ptr [ecx+4],edx
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     dword ptr [ebp-10h],edx
       mov     ebx,ecx
       mov     esi,edx
       mov     ecx,dword ptr [ebx]
       mov     eax,dword ptr [ebx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0xe6cf23
       mov     edx,dword ptr [ebx+4]
       cmp     edx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0xe6cf23
       lea     edi,[ebx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0xe6cf32
       lea     esi,[eax+edx*8+8]
       call    mscorlib_ni+0x31b160
       movs    dword ptr es:[edi],dword ptr [esi]
       inc     dword ptr [ebx+4]
       mov     eax,1
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,ebx
       mov     edx,esi
       call    System.Collections.Generic.List`1+Enumerator[[System.Collections.Generic.KeyValuePair`2[[System.__Canon, mscorlib],[System.UInt32, mscorlib]], mscorlib]].MoveNextRare()
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       call    mscorlib_ni+0x31b110
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       int     3
       nop
       nop
       nop
       nop
       nop
       ret
       int     3
       int     3
       push    edi
       push    esi
       nop
       nop
       nop
       mov     esi,ecx
       mov     eax,edx
       lea     edx,[esi]
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       push    ebx
       push    eax
       mov     dword ptr [ebp-10h],edx
       mov     ebx,ecx
       mov     esi,edx
       mov     ecx,dword ptr [ebx]
       mov     eax,dword ptr [ebx+8]
       cmp     eax,dword ptr [ecx+10h]
       jne     mscorlib_ni+0xe6d157
       mov     edx,dword ptr [ebx+4]
       cmp     edx,dword ptr [ecx+0Ch]
       jae     mscorlib_ni+0xe6d157
       lea     edi,[ebx+0Ch]
       mov     eax,dword ptr [ecx+4]
       cmp     edx,dword ptr [eax+4]
       jae     mscorlib_ni+0xe6d166
       lea     edx,[edx+edx*2]
       lea     esi,[eax+edx*4+8]
       movs    dword ptr es:[edi],dword ptr [esi]
       movs    dword ptr es:[edi],dword ptr [esi]
       call    mscorlib_ni+0x31b160
       inc     dword ptr [ebx+4]
       mov     eax,1
       pop     ecx
       pop     ebx
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     ecx,ebx
       mov     edx,esi
       call    System.Collections.Generic.List`1+Enumerator[[System.Collections.Generic.KeyValuePair`2[[System.__Canon, mscorlib],[System.Int64, mscorlib]], mscorlib]].MoveNextRare()
; Total bytes of code 4372
```
```assembly
; System.Text.StringBuilder.set_Length(Int32)
       IL_0000: ldarg.1
       IL_0001: ldc.i4.0
       IL_0002: bge.s IL_0019
       IL_0004: ldstr "value"
       IL_0009: ldstr "ArgumentOutOfRange_NegativeLength"
       IL_000e: call System.String System.Environment::GetResourceString(System.String)
       test    edi,edi
       jl      mscorlib_ni+0x10278a0
       cmp     edi,dword ptr [esi+14h]
       jg      mscorlib_ni+0x10278da
       mov     eax,dword ptr [esi+4]
       mov     ecx,dword ptr [eax+4]
       add     ecx,dword ptr [esi+10h]
       IL_003e: ldarg.1
       IL_003f: brtrue.s IL_0058
       test    edi,edi
       jne     mscorlib_ni+0x3f6ddf
       IL_0041: ldarg.0
       IL_0042: ldfld System.Text.StringBuilder System.Text.StringBuilder::m_ChunkPrevious
       IL_0047: brtrue.s IL_0058
       cmp     dword ptr [esi+8],0
       jne     mscorlib_ni+0x3f6ddf
       IL_0049: ldarg.0
       IL_004a: ldc.i4.0
       IL_004b: stfld System.Int32 System.Text.StringBuilder::m_ChunkLength
       xor     edx,edx
       mov     dword ptr [esi+0Ch],edx
       IL_0050: ldarg.0
       IL_0051: ldc.i4.0
       IL_0052: stfld System.Int32 System.Text.StringBuilder::m_ChunkOffset
       mov     dword ptr [esi+10h],edx
       IL_0057: ret
       IL_0058: ldarg.1
       IL_0059: ldarg.0
       IL_005a: call System.Int32 System.Text.StringBuilder::get_Length()
       IL_005f: sub
       IL_0060: stloc.1
       lea     esp,[ebp-8]
       pop     esi
       pop     edi
       pop     ebp
       ret
       mov     eax,edi
       mov     edx,dword ptr [esi+10h]
       add     edx,dword ptr [esi+0Ch]
       sub     eax,edx
       IL_0061: ldloc.1
       IL_0062: ldc.i4.0
       IL_0063: ble.s IL_006f
       test    eax,eax
       jg      mscorlib_ni+0x3f6e66
       IL_006f: ldarg.0
       IL_0070: ldarg.1
       IL_0071: call System.Text.StringBuilder System.Text.StringBuilder::FindChunkForIndex(System.Int32)
       IL_0076: stloc.2
       mov     dword ptr [ebp-10h],esi
       cmp     dword ptr [esi+10h],edi
       jle     mscorlib_ni+0x3f6e06
       mov     eax,dword ptr [ebp-10h]
       mov     eax,dword ptr [eax+8]
       mov     dword ptr [ebp-10h],eax
       mov     eax,dword ptr [ebp-10h]
       cmp     dword ptr [eax+10h],edi
       jg      mscorlib_ni+0x3f6df5
       IL_0077: ldloc.2
       IL_0078: ldarg.0
       IL_0079: beq.s IL_00bf
       cmp     dword ptr [ebp-10h],esi
       je      mscorlib_ni+0x3f6e56
       IL_007b: ldloc.0
       IL_007c: ldloc.2
       IL_007d: ldfld System.Int32 System.Text.StringBuilder::m_ChunkOffset
       IL_0082: sub
       IL_0083: stloc.3
       mov     eax,dword ptr [ebp-10h]
       sub     ecx,dword ptr [eax+10h]
       mov     edx,ecx
       IL_0084: ldloc.3
       IL_0085: newarr System.Char
       IL_008a: stloc.s V_4
       mov     ecx,offset mscorlib_ni+0x1632
       call    mscorlib_ni+0x31b0c8
       mov     dword ptr [ebp-0Ch],eax
       IL_008c: ldloc.2
       IL_008d: ldfld System.Char[] System.Text.StringBuilder::m_ChunkChars
       IL_0092: ldloc.s V_4
       IL_0094: ldloc.2
       IL_0095: ldfld System.Int32 System.Text.StringBuilder::m_ChunkLength
       mov     eax,dword ptr [ebp-10h]
       mov     ecx,dword ptr [eax+4]
       mov     eax,dword ptr [ebp-10h]
       push    dword ptr [eax+0Ch]
       mov     edx,dword ptr [ebp-0Ch]
       IL_009a: call System.Void System.Array::Copy(System.Array,System.Array,System.Int32)
       call    System.Array.Copy(System.Array, System.Array, Int32)
       IL_009f: ldarg.0
       IL_00a0: ldloc.s V_4
       IL_00a2: stfld System.Char[] System.Text.StringBuilder::m_ChunkChars
       mov     eax,dword ptr [ebp-0Ch]
       lea     edx,[esi+4]
       call    mscorlib_ni+0x31b010
       IL_00a7: ldarg.0
       IL_00a8: ldloc.2
       IL_00a9: ldfld System.Text.StringBuilder System.Text.StringBuilder::m_ChunkPrevious
       IL_00ae: stfld System.Text.StringBuilder System.Text.StringBuilder::m_ChunkPrevious
       mov     eax,dword ptr [ebp-10h]
       mov     eax,dword ptr [eax+8]
       lea     edx,[esi+8]
       call    mscorlib_ni+0x31b010
       IL_00b3: ldarg.0
       IL_00b4: ldloc.2
       IL_00b5: ldfld System.Int32 System.Text.StringBuilder::m_ChunkOffset
       IL_00ba: stfld System.Int32 System.Text.StringBuilder::m_ChunkOffset
       mov     eax,dword ptr [ebp-10h]
       mov     eax,dword ptr [eax+10h]
       mov     dword ptr [esi+10h],eax
       IL_00bf: ldarg.0
       IL_00c0: ldarg.1
       IL_00c1: ldloc.2
       IL_00c2: ldfld System.Int32 System.Text.StringBuilder::m_ChunkOffset
       IL_00c7: sub
       IL_00c8: stfld System.Int32 System.Text.StringBuilder::m_ChunkLength
       mov     eax,dword ptr [ebp-10h]
       sub     edi,dword ptr [eax+10h]
       mov     dword ptr [esi+0Ch],edi
       IL_00cd: ret
       lea     esp,[ebp-8]
       pop     esi
       pop     edi
       pop     ebp
       ret
       IL_0065: ldarg.0
       IL_0066: ldc.i4.0
       IL_0067: ldloc.1
       push    eax
       mov     ecx,esi
       xor     edx,edx
       IL_0068: call System.Text.StringBuilder System.Text.StringBuilder::Append(System.Char,System.Int32)
       IL_006d: pop
       call    System.Text.StringBuilder.Append(Char, Int32)
       IL_006e: ret
       lea     esp,[ebp-8]
       pop     esi
       pop     edi
       pop     ebp
       ret
       int     3
       push    ebp
       mov     ebp,esp
       push    edi
       push    esi
       sub     esp,1Ch
       mov     esi,ecx
       lea     edi,[ebp-24h]
       mov     ecx,6
       xor     eax,eax
       rep     stos dword ptr es:[edi]
       mov     ecx,esi
       mov     esi,ecx
       mov     edi,edx
       mov     ecx,dword ptr [esi+30h]
       mov     eax,dword ptr [ecx]
       mov     eax,dword ptr [eax+34h]
       call    dword ptr [eax]
       mov     dword ptr [ebp-24h],eax
       xor     edx,edx
       mov     dword ptr [ebp-20h],edx
       IL_0013: newobj System.Void System.ArgumentOutOfRangeException::.ctor(System.String,System.String)
       loopne  mscorlib_ni+0x3f6e27
       jge     mscorlib_ni+0x3f6e89
       add     byte ptr [ebp+eax-18h],dh
       IL_0018: throw
       IL_0019: ldarg.1
       IL_001a: ldarg.0
       IL_001b: call System.Int32 System.Text.StringBuilder::get_MaxCapacity()
       IL_0020: ble.s IL_0037
       IL_0022: ldstr "value"
       IL_0027: ldstr "ArgumentOutOfRange_SmallCapacity"
       IL_002c: call System.String System.Environment::GetResourceString(System.String)
       je      mscorlib_ni+0x3f6eb1
       call    System.Threading.Monitor.ThrowLockTakenException()
       lea     edx,[ebp-20h]
       mov     ecx,dword ptr [ebp-24h]
       call    System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
       mov     ecx,dword ptr [esi+30h]
       push    dword ptr [ebp+8]
       mov     edx,edi
       mov     eax,dword ptr [ecx]
       mov     eax,dword ptr [eax+2Ch]
       call    dword ptr [eax+14h]
       mov     dword ptr [ebp-18h],0
       mov     dword ptr [ebp-14h],0FCh
       push    offset mscorlib_ni+0x3f6efd
       IL_0031: newobj System.Void System.ArgumentOutOfRangeException::.ctor(System.String,System.String)
       jmp     mscorlib_ni+0x3f6ee1
       movzx   eax,byte ptr [ebp-20h]
       IL_0036: throw
       IL_0037: ldarg.0
       IL_0038: call System.Int32 System.Text.StringBuilder::get_Capacity()
       IL_003d: stloc.0
       loopne  mscorlib_ni+0x3f6e6b
       sal     byte ptr [eax+ecx-75h],4Dh
       fsub    st(0),st
       outs    dx,dword ptr [esi]
       bnd     call fword ptr fs:[eax-1]
       loopne  mscorlib_ni+0x3f6e82
       clc
       pop     esi
       pop     edi
       pop     ebp
       ret     4
       mov     dword ptr [ebp-14h],0
; Total bytes of code 349
```
```assembly
; System.Text.StringBuilder.Clear()
       IL_0000: ldarg.0
       IL_0001: ldc.i4.0
       mov     ecx,esi
       xor     edx,edx
       IL_0002: call System.Void System.Text.StringBuilder::set_Length(System.Int32)
       call    System.Text.StringBuilder.set_Length(Int32)
       IL_0007: ldarg.0
       IL_0008: ret
       mov     eax,esi
; Total bytes of code 11
```
**Abstract method**
System.IDisposable.Dispose()

