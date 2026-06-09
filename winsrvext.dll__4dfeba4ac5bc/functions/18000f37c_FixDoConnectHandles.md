# FixDoConnectHandles

- ea: `0x18000f37c`
- end: `0x18000f6c7`
- name: `FixDoConnectHandles`
- size: `843`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000ff10`

## callees

- `0x18000f37c`

## import_xrefs

- `ntdll!NtOpenProcess` at `0x18000f3fe`
- `ntdll!NtOpenProcess` at `0x18000f432`
- `ntdll!NtOpenProcess` at `0x18000f3fe`
- `ntdll!NtOpenProcess` at `0x18000f432`
- `ntdll!NtDuplicateObject` at `0x18000f473`
- `ntdll!NtDuplicateObject` at `0x18000f4aa`
- `ntdll!NtDuplicateObject` at `0x18000f4e1`
- `ntdll!NtDuplicateObject` at `0x18000f518`
- `ntdll!NtDuplicateObject` at `0x18000f54f`
- `ntdll!NtDuplicateObject` at `0x18000f582`
- `ntdll!NtDuplicateObject` at `0x18000f5b9`
- `ntdll!NtDuplicateObject` at `0x18000f473`
- `ntdll!NtDuplicateObject` at `0x18000f4aa`
- `ntdll!NtDuplicateObject` at `0x18000f4e1`
- `ntdll!NtDuplicateObject` at `0x18000f518`
- `ntdll!NtDuplicateObject` at `0x18000f54f`
- `ntdll!NtDuplicateObject` at `0x18000f582`
- `ntdll!NtDuplicateObject` at `0x18000f5b9`
- `ntdll!NtClose` at `0x18000f5d8`
- `ntdll!NtClose` at `0x18000f5ed`
- `ntdll!NtClose` at `0x18000f602`
- `ntdll!NtClose` at `0x18000f618`
- `ntdll!NtClose` at `0x18000f62d`
- `ntdll!NtClose` at `0x18000f642`
- `ntdll!NtClose` at `0x18000f693`
- `ntdll!NtClose` at `0x18000f6a8`
- `ntdll!NtClose` at `0x18000f5d8`
- `ntdll!NtClose` at `0x18000f5ed`
- `ntdll!NtClose` at `0x18000f602`
- `ntdll!NtClose` at `0x18000f618`
- `ntdll!NtClose` at `0x18000f62d`
- `ntdll!NtClose` at `0x18000f642`
- `ntdll!NtClose` at `0x18000f693`
- `ntdll!NtClose` at `0x18000f6a8`

## pseudocode

```c
__int64 __fastcall FixDoConnectHandles(__int64 a1)
{
  NTSTATUS v2; // edi
  void *v3; // rdx
  void *v4; // rdx
  void *v5; // rdx
  void *v6; // rdx
  void *v7; // rdx
  void *v8; // rdx
  void *v9; // rdx
  void *v11; // [rsp+40h] [rbp-49h] BYREF
  HANDLE v12; // [rsp+48h] [rbp-41h] BYREF
  HANDLE v13; // [rsp+50h] [rbp-39h] BYREF
  HANDLE v14; // [rsp+58h] [rbp-31h] BYREF
  HANDLE v15; // [rsp+60h] [rbp-29h] BYREF
  struct _CLIENT_ID ClientId; // [rsp+68h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-11h] BYREF
  void *ProcessHandle; // [rsp+F0h] [rbp+67h] BYREF
  void *TargetHandle; // [rsp+F8h] [rbp+6Fh] BYREF
  HANDLE Handle; // [rsp+100h] [rbp+77h] BYREF
  HANDLE v21; // [rsp+108h] [rbp+7Fh] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  TargetHandle = 0;
  Handle = 0;
  v21 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  ProcessHandle = 0;
  v15 = 0;
  ClientId.UniqueProcess = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  ClientId.UniqueThread = 0;
  if ( *(_DWORD *)(a1 + 64) )
  {
    ClientId.UniqueProcess = (HANDLE)*(int *)(a1 + 64);
    v2 = NtOpenProcess(&ProcessHandle, 0x40u, &ObjectAttributes, &ClientId);
    if ( v2 < 0 )
      goto LABEL_19;
  }
  if ( *(_DWORD *)(a1 + 224) )
  {
    ClientId.UniqueProcess = (HANDLE)*(int *)(a1 + 224);
    v2 = NtOpenProcess(&v15, 0x40u, &ObjectAttributes, &ClientId);
    if ( v2 < 0 )
      goto LABEL_19;
  }
  v3 = *(void **)(a1 + 8);
  if ( v3 )
  {
    v2 = NtDuplicateObject(ProcessHandle, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &TargetHandle, 0, 0, 2u);
    if ( v2 < 0 )
      goto LABEL_19;
  }
  v4 = *(void **)(a1 + 16);
  if ( v4 )
  {
    v2 = NtDuplicateObject(ProcessHandle, v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &Handle, 0, 0, 2u);
    if ( v2 < 0 )
      goto LABEL_19;
  }
  v5 = *(void **)(a1 + 24);
  if ( v5 )
  {
    v2 = NtDuplicateObject(ProcessHandle, v5, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &v21, 0, 0, 2u);
    if ( v2 < 0 )
      goto LABEL_19;
  }
  v6 = *(void **)(a1 + 32);
  if ( v6 )
  {
    v2 = NtDuplicateObject(ProcessHandle, v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &v11, 0, 0, 2u);
    if ( v2 < 0 )
      goto LABEL_19;
  }
  if ( (v7 = *(void **)(a1 + 40)) != 0
    && (v2 = NtDuplicateObject(ProcessHandle, v7, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &v12, 0, 0, 2u), v2 < 0)
    || (v8 = *(void **)(a1 + 48)) != 0
    && (v2 = NtDuplicateObject(ProcessHandle, v8, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &v13, 0, 0, 2u), v2 < 0)
    || (v9 = *(void **)(a1 + 56)) != 0
    && (v2 = NtDuplicateObject(ProcessHandle, v9, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &v14, 0, 0, 2u), v2 < 0) )
  {
LABEL_19:
    if ( TargetHandle )
      NtClose(TargetHandle);
    if ( Handle )
      NtClose(Handle);
    if ( v21 )
      NtClose(v21);
    if ( v11 )
      NtClose(v12);
    if ( v13 )
      NtClose(v13);
    if ( v14 )
      NtClose(v14);
  }
  else
  {
    v2 = 0;
    *(_QWORD *)(a1 + 8) = TargetHandle;
    *(_QWORD *)(a1 + 16) = Handle;
    *(_QWORD *)(a1 + 24) = v21;
    *(_QWORD *)(a1 + 32) = v11;
    *(_QWORD *)(a1 + 40) = v12;
    *(_QWORD *)(a1 + 48) = v13;
    *(_QWORD *)(a1 + 56) = v14;
  }
  if ( ProcessHandle )
    NtClose(ProcessHandle);
  if ( v15 )
    NtClose(v15);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000f37c  push    rbp
0x18000f37e  push    rbx
0x18000f37f  push    rsi
0x18000f380  push    rdi
0x18000f381  push    r14
0x18000f383  push    r15
0x18000f385  lea     rbp, [rsp-2Fh]
0x18000f38a  sub     rsp, 0B8h
0x18000f391  xor     esi, esi
0x18000f393  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000f39b  xorps   xmm0, xmm0
0x18000f39e  mov     rbx, rcx
0x18000f3a1  mov     [rbp+57h+TargetHandle], rsi
0x18000f3a5  mov     [rbp+57h+Handle], rsi
0x18000f3a9  lea     r14d, [rsi+40h]
0x18000f3ad  mov     [rbp+57h+arg_18], rsi
0x18000f3b1  mov     [rbp+57h+var_A0], rsi
0x18000f3b5  mov     [rbp+57h+var_98], rsi
0x18000f3b9  mov     [rbp+57h+var_90], rsi
0x18000f3bd  mov     [rbp+57h+var_88], rsi
0x18000f3c1  mov     [rbp+57h+ProcessHandle], rsi
0x18000f3c5  mov     [rbp+57h+var_80], rsi
0x18000f3c9  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], rsi
0x18000f3cd  mov     [rbp+57h+ClientId.UniqueProcess], rsi
0x18000f3d1  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18000f3d5  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x18000f3d9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000f3de  mov     [rbp+57h+ClientId.UniqueThread], rsi
0x18000f3e2  cmp     [rcx+40h], esi
0x18000f3e5  jz      short loc_18000F414
0x18000f3e7  movsxd  rax, dword ptr [rcx+40h]
0x18000f3eb  lea     r9, [rbp+57h+ClientId]; ClientId
0x18000f3ef  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x18000f3f3  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x18000f3f7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000f3fb  mov     edx, r14d; DesiredAccess
0x18000f3fe  call    cs:__imp_NtOpenProcess
0x18000f405  nop     dword ptr [rax+rax+00h]
0x18000f40a  mov     edi, eax
0x18000f40c  test    eax, eax
0x18000f40e  js      loc_18000F5CF
0x18000f414  movsxd  rax, dword ptr [rbx+0E0h]
0x18000f41b  test    eax, eax
0x18000f41d  jz      short loc_18000F448
0x18000f41f  lea     r9, [rbp+57h+ClientId]; ClientId
0x18000f423  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x18000f427  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000f42b  mov     edx, r14d; DesiredAccess
0x18000f42e  lea     rcx, [rbp+57h+var_80]; ProcessHandle
0x18000f432  call    cs:__imp_NtOpenProcess
0x18000f439  nop     dword ptr [rax+rax+00h]
0x18000f43e  mov     edi, eax
0x18000f440  test    eax, eax
0x18000f442  js      loc_18000F5CF
0x18000f448  mov     rdx, [rbx+8]; SourceHandle
0x18000f44c  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000f450  mov     r14d, 2
0x18000f456  test    rdx, rdx
0x18000f459  jz      short loc_18000F489
0x18000f45b  mov     rcx, [rbp+57h+ProcessHandle]; SourceProcessHandle
0x18000f45f  lea     r9, [rbp+57h+TargetHandle]; TargetHandle
0x18000f463  mov     [rsp+0E0h+Options], r14d; Options
0x18000f468  mov     r8, r15; TargetProcessHandle
0x18000f46b  mov     [rsp+0E0h+HandleAttributes], esi; HandleAttributes
0x18000f46f  mov     [rsp+0E0h+DesiredAccess], esi; DesiredAccess
0x18000f473  call    cs:__imp_NtDuplicateObject
0x18000f47a  nop     dword ptr [rax+rax+00h]
0x18000f47f  mov     edi, eax
0x18000f481  test    eax, eax
0x18000f483  js      loc_18000F5CF
0x18000f489  mov     rdx, [rbx+10h]; SourceHandle
0x18000f48d  test    rdx, rdx
0x18000f490  jz      short loc_18000F4C0
0x18000f492  mov     rcx, [rbp+57h+ProcessHandle]; SourceProcessHandle
0x18000f496  lea     r9, [rbp+57h+Handle]; TargetHandle
0x18000f49a  mov     [rsp+0E0h+Options], r14d; Options
0x18000f49f  mov     r8, r15; TargetProcessHandle
0x18000f4a2  mov     [rsp+0E0h+HandleAttributes], esi; HandleAttributes
0x18000f4a6  mov     [rsp+0E0h+DesiredAccess], esi; DesiredAccess
0x18000f4aa  call    cs:__imp_NtDuplicateObject
0x18000f4b1  nop     dword ptr [rax+rax+00h]
0x18000f4b6  mov     edi, eax
0x18000f4b8  test    eax, eax
0x18000f4ba  js      loc_18000F5CF
0x18000f4c0  mov     rdx, [rbx+18h]; SourceHandle
0x18000f4c4  test    rdx, rdx
0x18000f4c7  jz      short loc_18000F4F7
0x18000f4c9  mov     rcx, [rbp+57h+ProcessHandle]; SourceProcessHandle
0x18000f4cd  lea     r9, [rbp+57h+arg_18]; TargetHandle
0x18000f4d1  mov     [rsp+0E0h+Options], r14d; Options
0x18000f4d6  mov     r8, r15; TargetProcessHandle
0x18000f4d9  mov     [rsp+0E0h+HandleAttributes], esi; HandleAttributes
0x18000f4dd  mov     [rsp+0E0h+DesiredAccess], esi; DesiredAccess
0x18000f4e1  call    cs:__imp_NtDuplicateObject
0x18000f4e8  nop     dword ptr [rax+rax+00h]
0x18000f4ed  mov     edi, eax
0x18000f4ef  test    eax, eax
0x18000f4f1  js      loc_18000F5CF
0x18000f4f7  mov     rdx, [rbx+20h]; SourceHandle
0x18000f4fb  test    rdx, rdx
0x18000f4fe  jz      short loc_18000F52E
0x18000f500  mov     rcx, [rbp+57h+ProcessHandle]; SourceProcessHandle
0x18000f504  lea     r9, [rbp+57h+var_A0]; TargetHandle
0x18000f508  mov     [rsp+0E0h+Options], r14d; Options
0x18000f50d  mov     r8, r15; TargetProcessHandle
0x18000f510  mov     [rsp+0E0h+HandleAttributes], esi; HandleAttributes
0x18000f514  mov     [rsp+0E0h+DesiredAccess], esi; DesiredAccess
0x18000f518  call    cs:__imp_NtDuplicateObject
0x18000f51f  nop     dword ptr [rax+rax+00h]
0x18000f524  mov     edi, eax
0x18000f526  test    eax, eax
0x18000f528  js      loc_18000F5CF
0x18000f52e  mov     rdx, [rbx+28h]; SourceHandle
0x18000f532  test    rdx, rdx
0x18000f535  jz      short loc_18000F561
0x18000f537  mov     rcx, [rbp+57h+ProcessHandle]; SourceProcessHandle
0x18000f53b  lea     r9, [rbp+57h+var_98]; TargetHandle
0x18000f53f  mov     [rsp+0E0h+Options], r14d; Options
0x18000f544  mov     r8, r15; TargetProcessHandle
0x18000f547  mov     [rsp+0E0h+HandleAttributes], esi; HandleAttributes
0x18000f54b  mov     [rsp+0E0h+DesiredAccess], esi; DesiredAccess
0x18000f54f  call    cs:__imp_NtDuplicateObject
0x18000f556  nop     dword ptr [rax+rax+00h]
0x18000f55b  mov     edi, eax
0x18000f55d  test    eax, eax
0x18000f55f  js      short loc_18000F5CF
0x18000f561  mov     rdx, [rbx+30h]; SourceHandle
0x18000f565  test    rdx, rdx
0x18000f568  jz      short loc_18000F594
0x18000f56a  mov     rcx, [rbp+57h+ProcessHandle]; SourceProcessHandle
0x18000f56e  lea     r9, [rbp+57h+var_90]; TargetHandle
0x18000f572  mov     [rsp+0E0h+Options], r14d; Options
0x18000f577  mov     r8, r15; TargetProcessHandle
0x18000f57a  mov     [rsp+0E0h+HandleAttributes], esi; HandleAttributes
0x18000f57e  mov     [rsp+0E0h+DesiredAccess], esi; DesiredAccess
0x18000f582  call    cs:__imp_NtDuplicateObject
0x18000f589  nop     dword ptr [rax+rax+00h]
0x18000f58e  mov     edi, eax
0x18000f590  test    eax, eax
0x18000f592  js      short loc_18000F5CF
0x18000f594  mov     rdx, [rbx+38h]; SourceHandle
0x18000f598  test    rdx, rdx
0x18000f59b  jz      loc_18000F650
0x18000f5a1  mov     rcx, [rbp+57h+ProcessHandle]; SourceProcessHandle
0x18000f5a5  lea     r9, [rbp+57h+var_88]; TargetHandle
0x18000f5a9  mov     [rsp+0E0h+Options], r14d; Options
0x18000f5ae  mov     r8, r15; TargetProcessHandle
0x18000f5b1  mov     [rsp+0E0h+HandleAttributes], esi; HandleAttributes
0x18000f5b5  mov     [rsp+0E0h+DesiredAccess], esi; DesiredAccess
0x18000f5b9  call    cs:__imp_NtDuplicateObject
0x18000f5c0  nop     dword ptr [rax+rax+00h]
0x18000f5c5  mov     edi, eax
0x18000f5c7  test    eax, eax
0x18000f5c9  jns     loc_18000F650
0x18000f5cf  mov     rcx, [rbp+57h+TargetHandle]; Handle
0x18000f5d3  test    rcx, rcx
0x18000f5d6  jz      short loc_18000F5E4
0x18000f5d8  call    cs:__imp_NtClose
0x18000f5df  nop     dword ptr [rax+rax+00h]
0x18000f5e4  mov     rcx, [rbp+57h+Handle]; Handle
0x18000f5e8  test    rcx, rcx
0x18000f5eb  jz      short loc_18000F5F9
0x18000f5ed  call    cs:__imp_NtClose
0x18000f5f4  nop     dword ptr [rax+rax+00h]
0x18000f5f9  mov     rcx, [rbp+57h+arg_18]; Handle
0x18000f5fd  test    rcx, rcx
0x18000f600  jz      short loc_18000F60E
0x18000f602  call    cs:__imp_NtClose
0x18000f609  nop     dword ptr [rax+rax+00h]
0x18000f60e  cmp     [rbp+57h+var_A0], rsi
0x18000f612  jz      short loc_18000F624
0x18000f614  mov     rcx, [rbp+57h+var_98]; Handle
0x18000f618  call    cs:__imp_NtClose
0x18000f61f  nop     dword ptr [rax+rax+00h]
0x18000f624  mov     rcx, [rbp+57h+var_90]; Handle
0x18000f628  test    rcx, rcx
0x18000f62b  jz      short loc_18000F639
0x18000f62d  call    cs:__imp_NtClose
0x18000f634  nop     dword ptr [rax+rax+00h]
0x18000f639  mov     rcx, [rbp+57h+var_88]; Handle
0x18000f63d  test    rcx, rcx
0x18000f640  jz      short loc_18000F68A
0x18000f642  call    cs:__imp_NtClose
0x18000f649  nop     dword ptr [rax+rax+00h]
0x18000f64e  jmp     short loc_18000F68A
0x18000f650  mov     edi, esi
0x18000f652  mov     rax, [rbp+57h+TargetHandle]
0x18000f656  mov     [rbx+8], rax
0x18000f65a  mov     rax, [rbp+57h+Handle]
0x18000f65e  mov     [rbx+10h], rax
0x18000f662  mov     rax, [rbp+57h+arg_18]
0x18000f666  mov     [rbx+18h], rax
0x18000f66a  mov     rax, [rbp+57h+var_A0]
0x18000f66e  mov     [rbx+20h], rax
0x18000f672  mov     rax, [rbp+57h+var_98]
0x18000f676  mov     [rbx+28h], rax
0x18000f67a  mov     rax, [rbp+57h+var_90]
0x18000f67e  mov     [rbx+30h], rax
0x18000f682  mov     rax, [rbp+57h+var_88]
0x18000f686  mov     [rbx+38h], rax
0x18000f68a  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x18000f68e  test    rcx, rcx
0x18000f691  jz      short loc_18000F69F
0x18000f693  call    cs:__imp_NtClose
0x18000f69a  nop     dword ptr [rax+rax+00h]
0x18000f69f  mov     rcx, [rbp+57h+var_80]; Handle
0x18000f6a3  test    rcx, rcx
0x18000f6a6  jz      short loc_18000F6B4
0x18000f6a8  call    cs:__imp_NtClose
0x18000f6af  nop     dword ptr [rax+rax+00h]
0x18000f6b4  mov     eax, edi
0x18000f6b6  add     rsp, 0B8h
0x18000f6bd  pop     r15
0x18000f6bf  pop     r14
0x18000f6c1  pop     rdi
0x18000f6c2  pop     rsi
0x18000f6c3  pop     rbx
0x18000f6c4  pop     rbp
0x18000f6c5  retn
```
