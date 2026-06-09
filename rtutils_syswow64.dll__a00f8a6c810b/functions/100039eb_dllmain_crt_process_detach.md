# dllmain_crt_process_detach

- ea: `0x100039eb`
- end: `0x10003aa1`
- name: `dllmain_crt_process_detach`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x10003880`

## callees

- `0x100039eb`
- `0x10003d3f`
- `0x10003dbe`
- `0x10003eac`
- `0x10003ed5`
- `0x10004055`
- `0x1000407a`
- `0x100040b6`
- `0x100040fc`
- `0x10004130`

## pseudocode

```c
BOOL __cdecl dllmain_crt_process_detach(int a1)
{
  BOOL v2; // esi
  int v3; // [esp+0h] [ebp-30h]
  int v4; // [esp+4h] [ebp-2Ch]
  int v5; // [esp+8h] [ebp-28h]
  int v6; // [esp+Ch] [ebp-24h]
  int v7; // [esp+10h] [ebp-20h]
  int ms_exc; // [esp+18h] [ebp-18h]
  int ms_exc_4; // [esp+1Ch] [ebp-14h]
  int ms_exc_8; // [esp+20h] [ebp-10h]
  int ms_exc_12; // [esp+24h] [ebp-Ch]
  int ms_exc_16; // [esp+28h] [ebp-8h]

  if ( dword_1000B0B0 <= 0 )
    return 0;
  --dword_1000B0B0;
  LOBYTE(v7) = __scrt_acquire_startup_lock();
  if ( __scrt_current_native_startup_state != 2 )
    __scrt_fastfail(7);
  __scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  _RTC_Terminate();
  __scrt_current_native_startup_state = 0;
  __scrt_release_startup_lock(v7);
  v2 = (unsigned __int8)__scrt_uninitialize_crt(a1, 0) != 0;
  __scrt_dllmain_uninitialize_critical(
    268450418,
    v3,
    v4,
    v5,
    v6,
    v7,
    v2,
    ms_exc,
    ms_exc_4,
    ms_exc_8,
    ms_exc_12,
    ms_exc_16,
    -2);
  return v2;
}

```

## disassembly

```asm
0x100039eb  push    10h
0x100039ed  push    offset stru_1000A710
0x100039f2  call    __SEH_prolog4
0x100039f7  mov     eax, dword_1000B0B0
0x100039fc  test    eax, eax
0x100039fe  jg      short loc_10003A04
0x10003a00  xor     eax, eax
0x10003a02  jmp     short loc_10003A74
0x10003a04  dec     eax
0x10003a05  mov     dword_1000B0B0, eax
0x10003a0a  xor     esi, esi
0x10003a0c  inc     esi
0x10003a0d  mov     [ebp+var_1C], esi
0x10003a10  mov     [ebp+ms_exc.registration.TryLevel], 0
0x10003a17  call    ___scrt_acquire_startup_lock
0x10003a1c  mov     byte ptr [ebp+var_20], al
0x10003a1f  mov     [ebp+ms_exc.registration.TryLevel], esi
0x10003a22  cmp     ___scrt_current_native_startup_state, 2
0x10003a29  jnz     short loc_10003A9A
0x10003a2b  call    ___scrt_dllmain_uninitialize_c
0x10003a30  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x10003a35  call    __RTC_Terminate
0x10003a3a  mov     ___scrt_current_native_startup_state, 0
0x10003a44  mov     [ebp+ms_exc.registration.TryLevel], 0
0x10003a4b  call    loc_10003A87
0x10003a50  push    0
0x10003a52  push    [ebp+arg_0]
0x10003a55  call    ___scrt_uninitialize_crt
0x10003a5a  pop     ecx
0x10003a5b  pop     ecx
0x10003a5c  xor     ecx, ecx
0x10003a5e  test    al, al
0x10003a60  cmovz   esi, ecx
0x10003a63  mov     [ebp+var_1C], esi
0x10003a66  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10003a6d  call    loc_10003A94
0x10003a72  mov     eax, esi
0x10003a74  mov     ecx, [ebp+ms_exc.registration.Next]
0x10003a77  mov     large fs:0, ecx
0x10003a7e  pop     ecx
0x10003a7f  pop     edi
0x10003a80  pop     esi
0x10003a81  pop     ebx
0x10003a82  leave
0x10003a83  retn
0x10003a84  mov     esi, [ebp+var_1C]
0x10003a87  push    [ebp+var_20]
0x10003a8a  call    ___scrt_release_startup_lock
0x10003a8f  pop     ecx
0x10003a90  retn
0x10003a91  mov     esi, [ebp+var_1C]
0x10003a94  call    ___scrt_dllmain_uninitialize_critical
0x10003a99  retn
0x10003a9a  push    7
0x10003a9c  call    ___scrt_fastfail
```
