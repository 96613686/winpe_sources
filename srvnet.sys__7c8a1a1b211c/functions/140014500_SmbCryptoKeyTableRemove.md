# SmbCryptoKeyTableRemove

- ea: `0x140014500`
- end: `0x1400145d4`
- name: `SmbCryptoKeyTableRemove`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400043c0`
- `0x140014500`
- `0x1400146a4`
- `0x14002a3e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001457c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400145af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001457c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400145af`
- `ksecdd!BCryptDestroyKey` at `0x140014568`
- `ksecdd!BCryptDestroyKey` at `0x14001459b`
- `ksecdd!BCryptDestroyKey` at `0x140014568`
- `ksecdd!BCryptDestroyKey` at `0x14001459b`

## pseudocode

```c
void __fastcall SmbCryptoKeyTableRemove(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  _QWORD v6[2]; // [rsp+20h] [rbp-28h] BYREF

  v6[1] = a2;
  v6[0] = a3;
  v4 = RfsHashTableLookup(a1, v6);
  v5 = v4;
  if ( v4 )
  {
    RfsHashTableRemove(a1, (_QWORD *)(v4 + 24), (__int64)v6, 0x10u);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v5 )
        BCryptDestroyKey(*(BCRYPT_KEY_HANDLE *)v5);
      ExFreePoolWithTag((PVOID)v5, 0x2332534Cu);
    }
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v5 + 16)) )
    {
      if ( *(_QWORD *)v5 )
        BCryptDestroyKey(*(BCRYPT_KEY_HANDLE *)v5);
      ExFreePoolWithTag((PVOID)v5, 0x2332534Cu);
    }
  }
}

```

## disassembly

```asm
0x140014500  mov     r11, rsp
0x140014503  mov     [r11+20h], rbx
0x140014507  push    rdi
0x140014508  sub     rsp, 40h
0x14001450c  mov     rax, cs:__security_cookie
0x140014513  xor     rax, rsp
0x140014516  mov     [rsp+48h+var_18], rax
0x14001451b  mov     [r11-20h], rdx
0x14001451f  mov     rdi, rcx
0x140014522  lea     rdx, [r11-28h]
0x140014526  mov     [r11-28h], r8
0x14001452a  call    RfsHashTableLookup
0x14001452f  mov     rbx, rax
0x140014532  test    rax, rax
0x140014535  jz      loc_1400145BB
0x14001453b  lea     rdx, [rax+18h]
0x14001453f  mov     r9d, 10h
0x140014545  lea     r8, [rsp+48h+var_28]
0x14001454a  mov     rcx, rdi
0x14001454d  call    RfsHashTableRemove
0x140014552  or      edi, 0FFFFFFFFh
0x140014555  mov     ecx, edi
0x140014557  lock xadd [rbx+10h], ecx
0x14001455c  add     ecx, edi
0x14001455e  jnz     short loc_140014588
0x140014560  mov     rcx, [rbx]; hKey
0x140014563  test    rcx, rcx
0x140014566  jz      short loc_140014574
0x140014568  call    cs:__imp_BCryptDestroyKey
0x14001456f  nop     dword ptr [rax+rax+00h]
0x140014574  mov     edx, 2332534Ch; Tag
0x140014579  mov     rcx, rbx; P
0x14001457c  call    cs:__imp_ExFreePoolWithTag
0x140014583  nop     dword ptr [rax+rax+00h]
0x140014588  mov     eax, edi
0x14001458a  lock xadd [rbx+10h], eax
0x14001458f  add     eax, edi
0x140014591  jnz     short loc_1400145BB
0x140014593  mov     rcx, [rbx]; hKey
0x140014596  test    rcx, rcx
0x140014599  jz      short loc_1400145A7
0x14001459b  call    cs:__imp_BCryptDestroyKey
0x1400145a2  nop     dword ptr [rax+rax+00h]
0x1400145a7  mov     edx, 2332534Ch; Tag
0x1400145ac  mov     rcx, rbx; P
0x1400145af  call    cs:__imp_ExFreePoolWithTag
0x1400145b6  nop     dword ptr [rax+rax+00h]
0x1400145bb  mov     rcx, [rsp+48h+var_18]
0x1400145c0  xor     rcx, rsp; StackCookie
0x1400145c3  call    __security_check_cookie
0x1400145c8  mov     rbx, [rsp+48h+arg_18]
0x1400145cd  add     rsp, 40h
0x1400145d1  pop     rdi
0x1400145d2  retn
```
