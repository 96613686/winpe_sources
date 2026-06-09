# JobStore::TakeBackupRestorePermissions(uchar *,uchar *)

- ea: `0x18006e92c`
- end: `0x18006ead7`
- name: `?TakeBackupRestorePermissions@JobStore@@AEBAJPEAE0@Z`
- size: `427`
- prototype: `__int64 __fastcall(JobStore *__hidden this, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18006b9e4`
- `0x18006c234`

## callees

- `0x180001520`
- `0x180043c20`
- `0x18006e92c`
- `0x18007e6d0`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18006e969`
- `ntdll!RtlAdjustPrivilege` at `0x18006e9fa`
- `ntdll!RtlAdjustPrivilege` at `0x18006ea9f`
- `ntdll!RtlAdjustPrivilege` at `0x18006e969`
- `ntdll!RtlAdjustPrivilege` at `0x18006e9fa`
- `ntdll!RtlAdjustPrivilege` at `0x18006ea9f`

## pseudocode

```c
__int64 __fastcall JobStore::TakeBackupRestorePermissions(JobStore *this, unsigned __int8 *a2, unsigned __int8 *a3)
{
  __int64 v5; // rcx
  NTSTATUS v6; // ebx
  __int64 v7; // r8
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned __int8 OldValue; // [rsp+30h] [rbp-29h] BYREF
  char v13; // [rsp+31h] [rbp-28h] BYREF
  unsigned __int8 v14; // [rsp+32h] [rbp-27h] BYREF
  char v15; // [rsp+33h] [rbp-26h] BYREF
  _DWORD v16[3]; // [rsp+34h] [rbp-25h] BYREF
  _BYTE v17[32]; // [rsp+40h] [rbp-19h] BYREF
  _DWORD *v18; // [rsp+60h] [rbp+7h]
  __int64 v19; // [rsp+68h] [rbp+Fh]
  char *v20; // [rsp+70h] [rbp+17h]
  __int64 v21; // [rsp+78h] [rbp+1Fh]
  char *v22; // [rsp+80h] [rbp+27h]
  __int64 v23; // [rsp+88h] [rbp+2Fh]

  OldValue = 0;
  v14 = 0;
  v6 = RtlAdjustPrivilege(0x11u, 1u, 0, &OldValue);
  if ( v6 >= 0 )
  {
    v6 = RtlAdjustPrivilege(0x12u, 1u, 0, &v14);
    if ( v6 >= 0 )
    {
      v8 = 0;
      *a2 = OldValue;
      *a3 = v14;
      return v8;
    }
    if ( (unsigned int)dword_1800BC358 > 4 && (unsigned __int8)tlgKeywordOn(v9, 0x400000000001LL) )
    {
      v13 = *a3;
      v15 = *a2;
      v22 = &v13;
      v20 = &v15;
      v18 = v16;
      v19 = v10;
      v16[0] = v6;
      v23 = 1;
      v21 = 1;
      tlgWriteTransfer_EventWriteTransfer(&dword_1800BC358, word_1800AD66A, 0, 0, 5, v17);
    }
    RtlAdjustPrivilege(0x11u, OldValue, 0, &OldValue);
  }
  else if ( (unsigned int)dword_1800BC358 > 4 && (unsigned __int8)tlgKeywordOn(v5, 0x400000000001LL) )
  {
    v13 = *a2;
    v19 = v7;
    v20 = &v13;
    v16[0] = v6;
    v18 = v16;
    v21 = 1;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800BC358, byte_1800AD9E5, 0, 0, v7, v17);
  }
  return v6 | 0x10000000u;
}

```

## disassembly

```asm
0x18006e92c  mov     [rsp-8+arg_0], rbx
0x18006e931  push    rbp
0x18006e932  push    rsi
0x18006e933  push    rdi
0x18006e934  lea     rbp, [rsp-47h]
0x18006e939  sub     rsp, 0A0h
0x18006e940  mov     rax, cs:__security_cookie
0x18006e947  xor     rax, rsp
0x18006e94a  mov     [rbp+57h+var_20], rax
0x18006e94e  mov     rsi, r8
0x18006e951  mov     [rbp+57h+OldValue], 0
0x18006e955  xor     r8d, r8d; ForThread
0x18006e958  mov     [rbp+57h+var_7E], 0
0x18006e95c  mov     rdi, rdx
0x18006e95f  lea     r9, [rbp+57h+OldValue]; OldValue
0x18006e963  mov     dl, 1; NewValue
0x18006e965  lea     ecx, [r8+11h]; Privilege
0x18006e969  call    cs:__imp_RtlAdjustPrivilege
0x18006e96f  mov     ebx, eax
0x18006e971  test    eax, eax
0x18006e973  jns     short loc_18006E9ED
0x18006e975  mov     eax, cs:dword_1800BC358
0x18006e97b  mov     r8d, 4
0x18006e981  cmp     eax, r8d
0x18006e984  jbe     short loc_18006E9E4
0x18006e986  mov     rdx, 400000000001h
0x18006e990  call    _tlgKeywordOn
0x18006e995  test    al, al
0x18006e997  jz      short loc_18006E9E4
0x18006e999  mov     al, [rdi]
0x18006e99b  lea     rdx, byte_1800AD9E5
0x18006e9a2  mov     [rbp+57h+var_7F], al
0x18006e9a5  lea     rcx, dword_1800BC358
0x18006e9ac  lea     rax, [rbp+57h+var_7F]
0x18006e9b0  mov     [rbp+57h+var_48], r8
0x18006e9b4  mov     [rbp+57h+var_40], rax
0x18006e9b8  xor     r9d, r9d
0x18006e9bb  lea     rax, [rbp+57h+var_7C]
0x18006e9bf  mov     [rbp+57h+var_7C], ebx
0x18006e9c2  mov     [rbp+57h+var_50], rax
0x18006e9c6  lea     rax, [rbp+57h+var_70]
0x18006e9ca  mov     [rsp+0B0h+var_88], rax
0x18006e9cf  mov     [rsp+0B0h+var_90], r8d
0x18006e9d4  xor     r8d, r8d
0x18006e9d7  mov     [rbp+57h+var_38], 1
0x18006e9df  call    _tlgWriteTransfer_EventWriteTransfer
0x18006e9e4  bts     ebx, 1Ch
0x18006e9e8  jmp     loc_18006EAB6
0x18006e9ed  xor     r8d, r8d; ForThread
0x18006e9f0  lea     r9, [rbp+57h+var_7E]; OldValue
0x18006e9f4  mov     dl, 1; NewValue
0x18006e9f6  lea     ecx, [r8+12h]; Privilege
0x18006e9fa  call    cs:__imp_RtlAdjustPrivilege
0x18006ea00  mov     ebx, eax
0x18006ea02  test    eax, eax
0x18006ea04  jns     loc_18006EAAA
0x18006ea0a  mov     eax, cs:dword_1800BC358
0x18006ea10  mov     r8d, 4
0x18006ea16  cmp     eax, r8d
0x18006ea19  jbe     short loc_18006EA91
0x18006ea1b  mov     rdx, 400000000001h
0x18006ea25  call    _tlgKeywordOn
0x18006ea2a  test    al, al
0x18006ea2c  jz      short loc_18006EA91
0x18006ea2e  mov     al, [rsi]
0x18006ea30  lea     rdx, word_1800AD66A
0x18006ea37  mov     [rbp+57h+var_7F], al
0x18006ea3a  lea     rcx, dword_1800BC358
0x18006ea41  mov     al, [rdi]
0x18006ea43  xor     r9d, r9d
0x18006ea46  mov     [rbp+57h+var_7D], al
0x18006ea49  lea     rax, [rbp+57h+var_7F]
0x18006ea4d  mov     [rbp+57h+var_30], rax
0x18006ea51  lea     rax, [rbp+57h+var_7D]
0x18006ea55  mov     [rbp+57h+var_40], rax
0x18006ea59  lea     rax, [rbp+57h+var_7C]
0x18006ea5d  mov     [rbp+57h+var_50], rax
0x18006ea61  lea     rax, [rbp+57h+var_70]
0x18006ea65  mov     [rbp+57h+var_48], r8
0x18006ea69  xor     r8d, r8d
0x18006ea6c  mov     [rsp+0B0h+var_88], rax
0x18006ea71  mov     [rsp+0B0h+var_90], 5
0x18006ea79  mov     [rbp+57h+var_7C], ebx
0x18006ea7c  mov     [rbp+57h+var_28], 1
0x18006ea84  mov     [rbp+57h+var_38], 1
0x18006ea8c  call    _tlgWriteTransfer_EventWriteTransfer
0x18006ea91  mov     dl, [rbp+57h+OldValue]; NewValue
0x18006ea94  lea     r9, [rbp+57h+OldValue]; OldValue
0x18006ea98  xor     r8d, r8d; ForThread
0x18006ea9b  lea     ecx, [r8+11h]; Privilege
0x18006ea9f  call    cs:__imp_RtlAdjustPrivilege
0x18006eaa5  jmp     loc_18006E9E4
0x18006eaaa  mov     al, [rbp+57h+OldValue]
0x18006eaad  xor     ebx, ebx
0x18006eaaf  mov     [rdi], al
0x18006eab1  mov     al, [rbp+57h+var_7E]
0x18006eab4  mov     [rsi], al
0x18006eab6  mov     eax, ebx
0x18006eab8  mov     rcx, [rbp+57h+var_20]
0x18006eabc  xor     rcx, rsp; StackCookie
0x18006eabf  call    __security_check_cookie
0x18006eac4  mov     rbx, [rsp+0B0h+arg_0]
0x18006eacc  add     rsp, 0A0h
0x18006ead3  pop     rdi
0x18006ead4  pop     rsi
0x18006ead5  pop     rbp
0x18006ead6  retn
```
