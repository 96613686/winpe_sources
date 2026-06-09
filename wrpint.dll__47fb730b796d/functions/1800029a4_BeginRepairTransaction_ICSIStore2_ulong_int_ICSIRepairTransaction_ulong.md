# BeginRepairTransaction(ICSIStore2 *,ulong,int,ICSIRepairTransaction * *,ulong *)

- ea: `0x1800029a4`
- end: `0x180002a41`
- name: `?BeginRepairTransaction@@YAJPEAUICSIStore2@@KHPEAPEAUICSIRepairTransaction@@PEAK@Z`
- size: `157`
- prototype: `__int64 __fastcall(struct ICSIStore2 *, __int64, int, struct ICSIRepairTransaction **, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180002d00`
- `0x1800031c0`
- `0x180003a40`

## callees

- `0x1800029a4`
- `0x18001b7b0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall BeginRepairTransaction(
        struct ICSIStore2 *a1,
        __int64 a2,
        int a3,
        struct ICSIRepairTransaction **a4,
        unsigned int *a5)
{
  __int64 result; // rax
  GUID v7; // [rsp+40h] [rbp-28h] BYREF

  v7 = GUID_NULL;
  if ( a3 && !a5 )
    return 2147942487LL;
  result = (*(__int64 (__fastcall **)(struct ICSIStore2 *, __int64, GUID *, _QWORD, GUID *, struct ICSIRepairTransaction **, unsigned int *))(*(_QWORD *)a1 + 24LL))(
             a1,
             a2,
             &v7,
             0,
             &GUID_b891714f_67db_4eca_8881_e5932a0f0f94,
             a4,
             a5);
  if ( (int)result >= 0 )
  {
    if ( a3 && *a5 == 2 )
      return 2147483658LL;
    else
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800029a4  mov     [rsp+arg_10], rbx
0x1800029a9  push    rdi
0x1800029aa  sub     rsp, 60h
0x1800029ae  mov     rax, cs:__security_cookie
0x1800029b5  xor     rax, rsp
0x1800029b8  mov     [rsp+68h+var_18], rax
0x1800029bd  mov     rbx, [rsp+68h+arg_20]
0x1800029c5  mov     edi, r8d
0x1800029c8  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800029cf  movdqu  [rsp+68h+var_28], xmm0
0x1800029d5  test    r8d, r8d
0x1800029d8  jz      short loc_1800029E6
0x1800029da  test    rbx, rbx
0x1800029dd  jnz     short loc_1800029E6
0x1800029df  mov     eax, 80070057h
0x1800029e4  jmp     short loc_180002A26
0x1800029e6  mov     rax, [rcx]
0x1800029e9  lea     r8, _GUID_b891714f_67db_4eca_8881_e5932a0f0f94
0x1800029f0  mov     [rsp+68h+var_38], rbx
0x1800029f5  mov     [rsp+68h+var_40], r9
0x1800029fa  xor     r9d, r9d
0x1800029fd  mov     [rsp+68h+var_48], r8
0x180002a02  lea     r8, [rsp+68h+var_28]
0x180002a07  mov     rax, [rax+18h]
0x180002a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a10  test    eax, eax
0x180002a12  js      short loc_180002A26
0x180002a14  test    edi, edi
0x180002a16  jz      short loc_180002A24
0x180002a18  cmp     dword ptr [rbx], 2
0x180002a1b  jnz     short loc_180002A24
0x180002a1d  mov     eax, 8000000Ah
0x180002a22  jmp     short loc_180002A26
0x180002a24  xor     eax, eax
0x180002a26  mov     rcx, [rsp+68h+var_18]
0x180002a2b  xor     rcx, rsp; StackCookie
0x180002a2e  call    __security_check_cookie
0x180002a33  mov     rbx, [rsp+68h+arg_10]
0x180002a3b  add     rsp, 60h
0x180002a3f  pop     rdi
0x180002a40  retn
```
