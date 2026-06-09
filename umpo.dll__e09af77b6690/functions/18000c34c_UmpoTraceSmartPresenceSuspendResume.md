# UmpoTraceSmartPresenceSuspendResume

- ea: `0x18000c34c`
- end: `0x18000c492`
- name: `UmpoTraceSmartPresenceSuspendResume`
- size: `326`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000c1b4`
- `0x18000c2fc`

## callees

- `0x18000c04c`
- `0x18000c34c`
- `0x18000d6cc`
- `0x180010070`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000c46f`
- `ntdll!EtwEventWrite` at `0x18000c46f`

## pseudocode

```c
__int64 __fastcall UmpoTraceSmartPresenceSuspendResume(char a1)
{
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  char v4; // r10
  char v6; // [rsp+30h] [rbp-79h] BYREF
  char v7; // [rsp+31h] [rbp-78h] BYREF
  char v8; // [rsp+32h] [rbp-77h] BYREF
  int v9; // [rsp+38h] [rbp-71h] BYREF
  int v10; // [rsp+40h] [rbp-69h] BYREF
  BOOL v11; // [rsp+44h] [rbp-65h] BYREF
  BOOL v12; // [rsp+48h] [rbp-61h] BYREF
  BOOL v13; // [rsp+4Ch] [rbp-5Dh] BYREF
  _QWORD v14[8]; // [rsp+50h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+90h] [rbp-19h] BYREF
  char *v16; // [rsp+B0h] [rbp+7h]
  __int64 v17; // [rsp+B8h] [rbp+Fh]
  char *v18; // [rsp+C0h] [rbp+17h]
  __int64 v19; // [rsp+C8h] [rbp+1Fh]
  char *v20; // [rsp+D0h] [rbp+27h]
  __int64 v21; // [rsp+D8h] [rbp+2Fh]
  int *v22; // [rsp+E0h] [rbp+37h]
  __int64 v23; // [rsp+E8h] [rbp+3Fh]

  v9 = UmpoSmartPresenceSuspendCount;
  v11 = a1 != 0;
  v13 = UmpoSmartPresenceModeDisabled == 0;
  v12 = UmpoGlobalUserPresent != 0;
  if ( (unsigned int)dword_180024190 > 5 && tlgKeywordOn() )
  {
    v6 = v2;
    v16 = &v6;
    v17 = 1;
    v18 = &v7;
    v20 = &v8;
    v10 = v9;
    v22 = &v10;
    v7 = v3;
    v19 = 1;
    v8 = v4;
    v21 = 1;
    v23 = 4;
    tlgWriteTransfer_EventWriteTransfer(v1, (unsigned __int8 *)&byte_18001F691, v2, v3, 6u, &v15);
  }
  v14[0] = &v11;
  v14[1] = 4;
  v14[2] = &v9;
  v14[3] = 4;
  v14[4] = &v12;
  v14[5] = 4;
  v14[6] = &v13;
  v14[7] = 4;
  return EtwEventWrite(UmpoProviderHandle, UMPO_EVT_SMART_USER_PRESENCE_SUSPENDRESUME, 4, v14);
}

```

## disassembly

```asm
0x18000c34c  mov     [rsp-8+arg_0], rdi
0x18000c351  push    rbp
0x18000c352  lea     rbp, [rsp-57h]
0x18000c357  sub     rsp, 100h
0x18000c35e  mov     rax, cs:__security_cookie
0x18000c365  xor     rax, rsp
0x18000c368  mov     [rbp+57h+var_10], rax
0x18000c36c  mov     eax, cs:UmpoSmartPresenceSuspendCount
0x18000c372  mov     r8b, cl
0x18000c375  mov     r9b, cs:UmpoSmartPresenceModeDisabled
0x18000c37c  mov     edi, 4
0x18000c381  mov     r10b, cs:UmpoGlobalUserPresent
0x18000c388  mov     [rbp+57h+var_C8], eax
0x18000c38b  xor     eax, eax
0x18000c38d  test    cl, cl
0x18000c38f  setnz   al
0x18000c392  mov     [rbp+57h+var_BC], eax
0x18000c395  xor     eax, eax
0x18000c397  test    r9b, r9b
0x18000c39a  setz    al
0x18000c39d  mov     [rbp+57h+var_B4], eax
0x18000c3a0  xor     eax, eax
0x18000c3a2  test    r10b, r10b
0x18000c3a5  setnz   al
0x18000c3a8  mov     [rbp+57h+var_B8], eax
0x18000c3ab  mov     eax, cs:dword_180024190
0x18000c3b1  cmp     eax, 5
0x18000c3b4  jbe     short loc_18000C42A
0x18000c3b6  call    _tlgKeywordOn
0x18000c3bb  test    al, al
0x18000c3bd  jz      short loc_18000C42A
0x18000c3bf  lea     rax, [rbp+57h+var_D0]
0x18000c3c3  mov     [rbp+57h+var_D0], r8b
0x18000c3c7  mov     [rbp+57h+var_50], rax
0x18000c3cb  lea     rdx, byte_18001F691; int
0x18000c3d2  lea     rax, [rbp+57h+var_CF]
0x18000c3d6  mov     [rbp+57h+var_48], 1
0x18000c3de  mov     [rbp+57h+var_40], rax
0x18000c3e2  lea     rax, [rbp+57h+var_CE]
0x18000c3e6  mov     [rbp+57h+var_30], rax
0x18000c3ea  mov     eax, [rbp+57h+var_C8]
0x18000c3ed  mov     [rbp+57h+var_C0], eax
0x18000c3f0  lea     rax, [rbp+57h+var_C0]
0x18000c3f4  mov     [rbp+57h+var_20], rax
0x18000c3f8  lea     rax, [rbp+57h+var_70]
0x18000c3fc  mov     [rsp+100h+var_D8], rax; __int64
0x18000c401  mov     [rsp+100h+var_E0], 6; ULONG
0x18000c409  mov     [rbp+57h+var_CF], r9b
0x18000c40d  mov     [rbp+57h+var_38], 1
0x18000c415  mov     [rbp+57h+var_CE], r10b
0x18000c419  mov     [rbp+57h+var_28], 1
0x18000c421  mov     [rbp+57h+var_18], rdi
0x18000c425  call    _tlgWriteTransfer_EventWriteTransfer
0x18000c42a  mov     rcx, cs:UmpoProviderHandle
0x18000c431  lea     rax, [rbp+57h+var_BC]
0x18000c435  mov     [rbp+57h+var_B0], rax
0x18000c439  lea     r9, [rbp+57h+var_B0]
0x18000c43d  lea     rax, [rbp+57h+var_C8]
0x18000c441  mov     [rbp+57h+var_A8], rdi
0x18000c445  mov     [rbp+57h+var_A0], rax
0x18000c449  lea     rdx, UMPO_EVT_SMART_USER_PRESENCE_SUSPENDRESUME
0x18000c450  lea     rax, [rbp+57h+var_B8]
0x18000c454  mov     [rbp+57h+var_98], rdi
0x18000c458  mov     [rbp+57h+var_90], rax
0x18000c45c  mov     r8d, edi
0x18000c45f  lea     rax, [rbp+57h+var_B4]
0x18000c463  mov     [rbp+57h+var_88], rdi
0x18000c467  mov     [rbp+57h+var_80], rax
0x18000c46b  mov     [rbp+57h+var_78], rdi
0x18000c46f  call    cs:__imp_EtwEventWrite
0x18000c475  mov     rcx, [rbp+57h+var_10]
0x18000c479  xor     rcx, rsp; StackCookie
0x18000c47c  call    __security_check_cookie
0x18000c481  mov     rdi, [rsp+100h+arg_0]
0x18000c489  add     rsp, 100h
0x18000c490  pop     rbp
0x18000c491  retn
```
