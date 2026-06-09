# dllmain_dispatch

- ea: `0x10003aa8`
- end: `0x10003bb1`
- name: `dllmain_dispatch`
- size: `265`
- prototype: `int __cdecl(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x10003bf0`

## callees

- `0x10003880`
- `0x10003aa8`
- `0x10003bb7`
- `0x10003e70`
- `0x10004130`
- `0x10004fe6`

## pseudocode

```c
int __cdecl dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  void *v4; // ebx
  int v5; // esi
  BOOL v6; // eax

  if ( !fdwReason && dword_1000B0B0 <= 0 )
    return 0;
  if ( fdwReason != 1 && fdwReason != 2 )
  {
    v4 = lpvReserved;
LABEL_9:
    v6 = DllMain(hinstDLL, fdwReason, v4);
    v5 = v6;
    if ( fdwReason == 1 && !v6 )
    {
      DllMain(hinstDLL, 0, v4);
      dllmain_crt_dispatch(hinstDLL, 0, v4);
      dllmain_raw(hinstDLL, 0, v4);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v5 = dllmain_crt_dispatch(hinstDLL, fdwReason, v4);
      if ( v5 )
        return dllmain_raw(hinstDLL, fdwReason, v4);
    }
    return v5;
  }
  v4 = lpvReserved;
  v5 = dllmain_raw(hinstDLL, fdwReason, lpvReserved);
  if ( v5 )
  {
    v5 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved);
    if ( v5 )
      goto LABEL_9;
  }
  return v5;
}

```

## disassembly

```asm
0x10003aa8  push    0Ch
0x10003aaa  push    offset stru_1000A738
0x10003aaf  call    __SEH_prolog4
0x10003ab4  mov     edi, [ebp+fdwReason]
0x10003ab7  test    edi, edi
0x10003ab9  jnz     short loc_10003ACA
0x10003abb  cmp     dword_1000B0B0, edi
0x10003ac1  jg      short loc_10003ACA
0x10003ac3  xor     eax, eax
0x10003ac5  jmp     loc_10003BA1
0x10003aca  mov     [ebp+ms_exc.registration.TryLevel], 0
0x10003ad1  cmp     edi, 1
0x10003ad4  jz      short loc_10003AE0
0x10003ad6  cmp     edi, 2
0x10003ad9  jz      short loc_10003AE0
0x10003adb  mov     ebx, [ebp+lpvReserved]
0x10003ade  jmp     short loc_10003B11
0x10003ae0  mov     ebx, [ebp+lpvReserved]
0x10003ae3  push    ebx
0x10003ae4  push    edi
0x10003ae5  push    [ebp+hinstDLL]
0x10003ae8  call    dllmain_raw
0x10003aed  mov     esi, eax
0x10003aef  mov     [ebp+var_1C], esi
0x10003af2  test    esi, esi
0x10003af4  jz      loc_10003B98
0x10003afa  push    ebx
0x10003afb  push    edi
0x10003afc  push    [ebp+hinstDLL]
0x10003aff  call    dllmain_crt_dispatch
0x10003b04  mov     esi, eax
0x10003b06  mov     [ebp+var_1C], esi
0x10003b09  test    esi, esi
0x10003b0b  jz      loc_10003B98
0x10003b11  push    ebx; lpvReserved
0x10003b12  push    edi; fdwReason
0x10003b13  push    [ebp+hinstDLL]; hinstDLL
0x10003b16  call    _DllMain@12; DllMain(x,x,x)
0x10003b1b  mov     esi, eax
0x10003b1d  mov     [ebp+var_1C], esi
0x10003b20  cmp     edi, 1
0x10003b23  jnz     short loc_10003B47
0x10003b25  test    esi, esi
0x10003b27  jnz     short loc_10003B47
0x10003b29  push    ebx; lpvReserved
0x10003b2a  push    eax; fdwReason
0x10003b2b  push    [ebp+hinstDLL]; hinstDLL
0x10003b2e  call    _DllMain@12; DllMain(x,x,x)
0x10003b33  push    ebx
0x10003b34  push    esi
0x10003b35  push    [ebp+hinstDLL]
0x10003b38  call    dllmain_crt_dispatch
0x10003b3d  push    ebx
0x10003b3e  push    esi
0x10003b3f  push    [ebp+hinstDLL]
0x10003b42  call    dllmain_raw
0x10003b47  test    edi, edi
0x10003b49  jz      short loc_10003B50
0x10003b4b  cmp     edi, 3
0x10003b4e  jnz     short loc_10003B98
0x10003b50  push    ebx
0x10003b51  push    edi
0x10003b52  push    [ebp+hinstDLL]
0x10003b55  call    dllmain_crt_dispatch
0x10003b5a  mov     esi, eax
0x10003b5c  mov     [ebp+var_1C], esi
0x10003b5f  test    esi, esi
0x10003b61  jz      short loc_10003B98
0x10003b63  push    ebx
0x10003b64  push    edi
0x10003b65  push    [ebp+hinstDLL]
0x10003b68  call    dllmain_raw
0x10003b6d  mov     esi, eax
0x10003b6f  jmp     short loc_10003B95
0x10003b71  mov     ecx, [ebp+ms_exc.exc_ptr]
0x10003b74  mov     eax, [ecx]
0x10003b76  push    ecx; ExceptionPtr
0x10003b77  push    dword ptr [eax]; ExceptionNum
0x10003b79  push    offset dllmain_crt_dispatch; int
0x10003b7e  push    [ebp+lpvReserved]; int
0x10003b81  push    [ebp+fdwReason]; int
0x10003b84  push    [ebp+hinstDLL]; int
0x10003b87  call    ___scrt_dllmain_exception_filter
0x10003b8c  add     esp, 18h
0x10003b8f  retn
0x10003b90  mov     esp, [ebp+ms_exc.old_esp]
0x10003b93  xor     esi, esi
0x10003b95  mov     [ebp+var_1C], esi
0x10003b98  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10003b9f  mov     eax, esi
0x10003ba1  mov     ecx, [ebp+ms_exc.registration.Next]
0x10003ba4  mov     large fs:0, ecx
0x10003bab  pop     ecx
0x10003bac  pop     edi
0x10003bad  pop     esi
0x10003bae  pop     ebx
0x10003baf  leave
0x10003bb0  retn
```
