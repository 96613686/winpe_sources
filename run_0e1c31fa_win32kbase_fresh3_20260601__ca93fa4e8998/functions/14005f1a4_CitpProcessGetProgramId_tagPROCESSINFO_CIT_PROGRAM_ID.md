# CitpProcessGetProgramId(tagPROCESSINFO *,_CIT_PROGRAM_ID *)

- ea: `0x14005f1a4`
- end: `0x14005f51a`
- name: `?CitpProcessGetProgramId@@YAJPEAUtagPROCESSINFO@@PEAU_CIT_PROGRAM_ID@@@Z`
- size: `886`
- prototype: `int(struct tagPROCESSINFO *, struct _CIT_PROGRAM_ID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x14005eaa4`

## callees

- `0x1400411c0`
- `0x1400449b0`
- `0x14005f1a4`
- `0x14005f608`
- `0x14005f680`
- `0x1401b0434`
- `0x1401c4d1c`
- `0x140238b10`
- `0x140239180`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14005f215`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14005f215`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x14005f1fb`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x14005f1fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f399`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f399`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14005f40d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14005f40d`
- `ntoskrnl!RtlImageNtHeader` at `0x14005f2cd`
- `ntoskrnl!RtlImageNtHeader` at `0x14005f2cd`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14005f381`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14005f381`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x14005f45b`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x14005f45b`
- `ntoskrnl!KeAttachProcess` at `0x14005f23d`
- `ntoskrnl!KeAttachProcess` at `0x14005f23d`
- `ntoskrnl!SeLocateProcessImageName` at `0x14005f275`
- `ntoskrnl!SeLocateProcessImageName` at `0x14005f275`
- `ntoskrnl!KeDetachProcess` at `0x14005f3bc`
- `ntoskrnl!KeDetachProcess` at `0x14005f3bc`

## pseudocode

```c
__int64 __fastcall CitpProcessGetProgramId(PRKPROCESS *a1, struct _CIT_PROGRAM_ID *a2)
{
  char v4; // r12
  void *v5; // rsi
  PACCESS_TOKEN v6; // r15
  const char *v7; // rdx
  __int64 CurrentProcessWin32Process; // rax
  struct tagPROCESSINFO *v9; // rdx
  wchar_t *v10; // rdi
  NTSTATUS v11; // eax
  int v12; // edi
  PIMAGE_NT_HEADERS v13; // rax
  DWORD TimeDateStamp; // edi
  unsigned int v15; // r8d
  int v16; // ecx
  int v18; // eax
  const char *v19; // rdx
  void *v20; // rax
  wchar_t *String; // [rsp+38h] [rbp-210h] BYREF
  PUNICODE_STRING pImageFileName; // [rsp+40h] [rbp-208h] BYREF
  PVOID BaseAddress; // [rsp+48h] [rbp-200h]
  size_t Size; // [rsp+50h] [rbp-1F8h] BYREF
  size_t v25; // [rsp+58h] [rbp-1F0h] BYREF
  void *v26; // [rsp+60h] [rbp-1E8h]
  PACCESS_TOKEN v27; // [rsp+68h] [rbp-1E0h]
  DWORD v28; // [rsp+70h] [rbp-1D8h]
  int v29; // [rsp+74h] [rbp-1D4h]
  _BYTE v30[144]; // [rsp+80h] [rbp-1C8h] BYREF
  _BYTE Src[256]; // [rsp+110h] [rbp-138h] BYREF

  v4 = 0;
  pImageFileName = 0;
  String = 0;
  v5 = 0;
  v26 = 0;
  v6 = 0;
  v27 = 0;
  BaseAddress = (PVOID)PsGetProcessSectionBaseAddress(*a1);
  if ( !BaseAddress )
  {
    v12 = -1073741637;
    v15 = 1764;
    goto LABEL_17;
  }
  CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
  v9 = (struct tagPROCESSINFO *)CurrentProcessWin32Process;
  if ( CurrentProcessWin32Process )
    v9 = (struct tagPROCESSINFO *)(-(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0) & CurrentProcessWin32Process);
  if ( a1 != (PRKPROCESS *)v9 )
  {
    KeAttachProcess(*a1);
    v4 = 1;
  }
  if ( (((unsigned __int8)*((_DWORD *)a1 + 202) >> 4) & 3) != 1 )
    goto LABEL_7;
  v6 = PsReferencePrimaryToken(*a1);
  v27 = v6;
  Size = 256;
  v25 = 130;
  v18 = RtlQueryPackageIdentity(v6, Src, &Size, v30, &v25, 0);
  if ( v18 < 0 )
  {
    CitpLogFailureWorker(v18, v19, 0x719u);
LABEL_7:
    v10 = 0;
    goto LABEL_8;
  }
  v10 = (wchar_t *)Win32AllocPoolZInitImpl(0x100u, Size, 0x49637355u);
  String = v10;
  v20 = Win32AllocPoolZInitImpl(0x100u, v25, 0x49637355u);
  v5 = v20;
  v26 = v20;
  if ( !v10 || !v20 )
  {
    v12 = -1073741670;
    v15 = 1806;
LABEL_17:
    v16 = v12;
LABEL_18:
    CitpLogFailureWorker(v16, v7, v15);
    goto LABEL_19;
  }
  memmove(v10, Src, Size);
  wcsupr(v10);
  memmove(v5, v30, v25);
LABEL_8:
  if ( v10 )
    goto LABEL_13;
  v11 = SeLocateProcessImageName(*a1, &pImageFileName);
  v12 = v11;
  if ( v11 < 0 )
  {
    pImageFileName = 0;
    v15 = 1830;
    v16 = v11;
    goto LABEL_18;
  }
  if ( !pImageFileName->Length )
  {
    v12 = -1073741637;
    goto LABEL_19;
  }
  v12 = CitpStringDuplicate(&String, pImageFileName->Buffer, (unsigned __int64)pImageFileName->Length >> 1);
  if ( v12 < 0 )
    goto LABEL_19;
  wcsupr(String);
LABEL_13:
  v13 = RtlImageNtHeader(BaseAddress);
  TimeDateStamp = v13->FileHeader.TimeDateStamp;
  v28 = TimeDateStamp;
  LODWORD(BaseAddress) = v13->OptionalHeader.CheckSum;
  v29 = (int)BaseAddress;
  if ( v5 )
    wcsupr((wchar_t *)v5);
  *(_QWORD *)a2 = String;
  String = 0;
  *((_QWORD *)a2 + 1) = v5;
  v5 = 0;
  *((_DWORD *)a2 + 6) = TimeDateStamp;
  *((_DWORD *)a2 + 7) = (_DWORD)BaseAddress;
  *((_DWORD *)a2 + 8) = (*((_DWORD *)a1 + 202) >> 4) & 3;
  *((_QWORD *)a2 + 2) = CitpProgramIdCalculateHash(a2);
  v12 = 0;
LABEL_19:
  if ( v6 )
    PsDereferencePrimaryToken(v6);
  if ( pImageFileName )
    ExFreePoolWithTag(pImageFileName, 0);
  GreDeleteFastMutex(String);
  GreDeleteFastMutex(v5);
  if ( v4 )
    KeDetachProcess();
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14005f1a4  mov     [rsp+arg_10], rbx
0x14005f1a9  mov     [rsp+arg_18], rsi
0x14005f1ae  push    rdi
0x14005f1af  push    r12
0x14005f1b1  push    r13
0x14005f1b3  push    r14
0x14005f1b5  push    r15
0x14005f1b7  sub     rsp, 220h
0x14005f1be  mov     rax, cs:__security_cookie
0x14005f1c5  xor     rax, rsp
0x14005f1c8  mov     [rsp+248h+var_38], rax
0x14005f1d0  mov     r13, rdx
0x14005f1d3  mov     r14, rcx
0x14005f1d6  xor     ebx, ebx
0x14005f1d8  mov     r12b, bl
0x14005f1db  mov     [rsp+248h+var_218], bl
0x14005f1df  mov     [rsp+248h+pImageFileName], rbx
0x14005f1e4  mov     [rsp+248h+String], rbx
0x14005f1e9  mov     esi, ebx
0x14005f1eb  mov     [rsp+248h+var_1E8], rbx
0x14005f1f0  mov     r15d, ebx
0x14005f1f3  mov     [rsp+248h+var_1E0], rbx
0x14005f1f8  mov     rcx, [rcx]
0x14005f1fb  call    cs:__imp_PsGetProcessSectionBaseAddress
0x14005f202  nop     dword ptr [rax+rax+00h]
0x14005f207  mov     [rsp+248h+BaseAddress], rax
0x14005f20c  test    rax, rax
0x14005f20f  jz      loc_14005F4EE
0x14005f215  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14005f21c  nop     dword ptr [rax+rax+00h]
0x14005f221  mov     rdx, rax
0x14005f224  test    rax, rax
0x14005f227  jz      short loc_14005F235
0x14005f229  mov     rax, [rax]
0x14005f22c  neg     rax
0x14005f22f  sbb     rcx, rcx
0x14005f232  and     rdx, rcx
0x14005f235  cmp     r14, rdx
0x14005f238  jz      short loc_14005F251
0x14005f23a  mov     rcx, [r14]; Process
0x14005f23d  call    cs:__imp_KeAttachProcess
0x14005f244  nop     dword ptr [rax+rax+00h]
0x14005f249  mov     r12b, 1
0x14005f24c  mov     [rsp+248h+var_218], r12b
0x14005f251  mov     eax, [r14+328h]
0x14005f258  shr     al, 4
0x14005f25b  and     al, 3
0x14005f25d  cmp     al, 1
0x14005f25f  jz      loc_14005F40A
0x14005f265  mov     rdi, rbx
0x14005f268  test    rdi, rdi
0x14005f26b  jnz     short loc_14005F2C8
0x14005f26d  lea     rdx, [rsp+248h+pImageFileName]; pImageFileName
0x14005f272  mov     rcx, [r14]; Process
0x14005f275  call    cs:__imp_SeLocateProcessImageName
0x14005f27c  nop     dword ptr [rax+rax+00h]
0x14005f281  mov     edi, eax
0x14005f283  test    eax, eax
0x14005f285  js      loc_14005F3F8
0x14005f28b  mov     rax, [rsp+248h+pImageFileName]
0x14005f290  movzx   ecx, word ptr [rax]
0x14005f293  test    cx, cx
0x14005f296  jz      loc_14005F510
0x14005f29c  mov     r8d, ecx
0x14005f29f  shr     r8, 1; unsigned __int64
0x14005f2a2  mov     rdx, rax
0x14005f2a5  mov     rdx, [rax+8]; unsigned __int16 *
0x14005f2a9  lea     rcx, [rsp+248h+String]; unsigned __int16 **
0x14005f2ae  call    ?CitpStringDuplicate@@YAJPEAPEAGPEBG_K@Z; CitpStringDuplicate(ushort * *,ushort const *,unsigned __int64)
0x14005f2b3  mov     edi, eax
0x14005f2b5  test    eax, eax
0x14005f2b7  js      loc_14005F379
0x14005f2bd  mov     rcx, [rsp+248h+String]; String
0x14005f2c2  call    _wcsupr
0x14005f2c7  nop
0x14005f2c8  mov     rcx, [rsp+248h+BaseAddress]; BaseAddress
0x14005f2cd  call    cs:__imp_RtlImageNtHeader
0x14005f2d4  nop     dword ptr [rax+rax+00h]
0x14005f2d9  mov     edi, [rax+8]
0x14005f2dc  mov     [rsp+248h+var_1D8], edi
0x14005f2e0  mov     eax, [rax+58h]
0x14005f2e3  mov     dword ptr [rsp+248h+BaseAddress], eax
0x14005f2e7  mov     [rsp+248h+var_1D4], eax
0x14005f2eb  jmp     short loc_14005F317
0x14005f2ed  mov     edi, eax
0x14005f2ef  mov     eax, 0C0000001h
0x14005f2f4  test    edi, edi
0x14005f2f6  cmovns  edi, eax
0x14005f2f9  mov     r8d, 753h; unsigned int
0x14005f2ff  mov     ecx, edi; int
0x14005f301  call    ?CitpLogFailureWorker@@YAXJPEBDI@Z; CitpLogFailureWorker(long,char const *,uint)
0x14005f306  mov     r12b, [rsp+248h+var_218]
0x14005f30b  mov     rsi, [rsp+248h+var_1E8]
0x14005f310  mov     r15, [rsp+248h+var_1E0]
0x14005f315  jmp     short loc_14005F379
0x14005f317  test    rsi, rsi
0x14005f31a  jz      short loc_14005F324
0x14005f31c  mov     rcx, rsi; String
0x14005f31f  call    _wcsupr
0x14005f324  mov     rax, [rsp+248h+String]
0x14005f329  mov     [r13+0], rax
0x14005f32d  mov     [rsp+248h+String], rbx
0x14005f332  mov     [r13+8], rsi
0x14005f336  mov     rsi, rbx
0x14005f339  mov     [r13+18h], edi
0x14005f33d  mov     eax, dword ptr [rsp+248h+BaseAddress]
0x14005f341  mov     [r13+1Ch], eax
0x14005f345  mov     eax, [r14+328h]
0x14005f34c  shr     rax, 4
0x14005f350  and     eax, 3
0x14005f353  mov     [r13+20h], eax
0x14005f357  mov     rcx, r13; struct _CIT_PROGRAM_ID *
0x14005f35a  call    ?CitpProgramIdCalculateHash@@YA_KPEBU_CIT_PROGRAM_ID@@@Z; CitpProgramIdCalculateHash(_CIT_PROGRAM_ID const *)
0x14005f35f  mov     [r13+10h], rax
0x14005f363  mov     edi, ebx
0x14005f365  jmp     short loc_14005F379
0x14005f367  mov     edi, 0C000009Ah
0x14005f36c  mov     r8d, 70Eh; unsigned int
0x14005f372  mov     ecx, edi; int
0x14005f374  call    ?CitpLogFailureWorker@@YAXJPEBDI@Z; CitpLogFailureWorker(long,char const *,uint)
0x14005f379  test    r15, r15
0x14005f37c  jz      short loc_14005F38D
0x14005f37e  mov     rcx, r15; PrimaryToken
0x14005f381  call    cs:__imp_PsDereferencePrimaryToken
0x14005f388  nop     dword ptr [rax+rax+00h]
0x14005f38d  mov     rcx, [rsp+248h+pImageFileName]; P
0x14005f392  test    rcx, rcx
0x14005f395  jz      short loc_14005F3A5
0x14005f397  xor     edx, edx; Tag
0x14005f399  call    cs:__imp_ExFreePoolWithTag
0x14005f3a0  nop     dword ptr [rax+rax+00h]
0x14005f3a5  mov     rcx, [rsp+248h+String]; Buffer
0x14005f3aa  call    GreDeleteFastMutex
0x14005f3af  mov     rcx, rsi; Buffer
0x14005f3b2  call    GreDeleteFastMutex
0x14005f3b7  test    r12b, r12b
0x14005f3ba  jz      short loc_14005F3C8
0x14005f3bc  call    cs:__imp_KeDetachProcess
0x14005f3c3  nop     dword ptr [rax+rax+00h]
0x14005f3c8  mov     eax, edi
0x14005f3ca  mov     rcx, [rsp+248h+var_38]
0x14005f3d2  xor     rcx, rsp; StackCookie
0x14005f3d5  call    __security_check_cookie
0x14005f3da  lea     r11, [rsp+248h+var_28]
0x14005f3e2  mov     rbx, [r11+40h]
0x14005f3e6  mov     rsi, [r11+48h]
0x14005f3ea  mov     rsp, r11
0x14005f3ed  pop     r15
0x14005f3ef  pop     r14
0x14005f3f1  pop     r13
0x14005f3f3  pop     r12
0x14005f3f5  pop     rdi
0x14005f3f6  retn
0x14005f3f8  mov     [rsp+248h+pImageFileName], rbx
0x14005f3fd  mov     r8d, 726h
0x14005f403  mov     ecx, eax
0x14005f405  jmp     loc_14005F374
0x14005f40a  mov     rcx, [r14]; Process
0x14005f40d  call    cs:__imp_PsReferencePrimaryToken
0x14005f414  nop     dword ptr [rax+rax+00h]
0x14005f419  mov     r15, rax
0x14005f41c  mov     [rsp+248h+var_1E0], rax
0x14005f421  mov     edi, 100h
0x14005f426  mov     [rsp+248h+Size], rdi
0x14005f42b  mov     [rsp+248h+var_1F0], 82h
0x14005f434  mov     [rsp+248h+var_220], rbx
0x14005f439  lea     rax, [rsp+248h+var_1F0]
0x14005f43e  mov     [rsp+248h+var_228], rax
0x14005f443  lea     r9, [rsp+248h+var_1C8]
0x14005f44b  lea     r8, [rsp+248h+Size]
0x14005f450  lea     rdx, [rsp+248h+Src]
0x14005f458  mov     rcx, r15
0x14005f45b  call    cs:__imp_RtlQueryPackageIdentity
0x14005f462  nop     dword ptr [rax+rax+00h]
0x14005f467  test    eax, eax
0x14005f469  js      loc_14005F4FE
0x14005f46f  mov     esi, 49637355h
0x14005f474  mov     r8d, esi; unsigned int
0x14005f477  mov     rdx, [rsp+248h+Size]; unsigned __int64
0x14005f47c  mov     ecx, edi; unsigned __int64
0x14005f47e  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14005f483  mov     rdi, rax
0x14005f486  mov     [rsp+248h+String], rax
0x14005f48b  mov     r8d, esi; unsigned int
0x14005f48e  mov     rdx, [rsp+248h+var_1F0]; unsigned __int64
0x14005f493  mov     ecx, 100h; unsigned __int64
0x14005f498  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14005f49d  mov     rsi, rax
0x14005f4a0  mov     [rsp+248h+var_1E8], rax
0x14005f4a5  test    rdi, rdi
0x14005f4a8  jz      loc_14005F367
0x14005f4ae  test    rax, rax
0x14005f4b1  jz      loc_14005F367
0x14005f4b7  mov     r8, [rsp+248h+Size]; Size
0x14005f4bc  lea     rdx, [rsp+248h+Src]; Src
0x14005f4c4  mov     rcx, rdi; void *
0x14005f4c7  call    memmove
0x14005f4cc  mov     rcx, rdi; String
0x14005f4cf  call    _wcsupr
0x14005f4d4  mov     r8, [rsp+248h+var_1F0]; Size
0x14005f4d9  lea     rdx, [rsp+248h+var_1C8]; Src
0x14005f4e1  mov     rcx, rsi; void *
0x14005f4e4  call    memmove
0x14005f4e9  jmp     loc_14005F268
0x14005f4ee  mov     edi, 0C00000BBh
0x14005f4f3  mov     r8d, 6E4h
0x14005f4f9  jmp     loc_14005F372
0x14005f4fe  mov     r8d, 719h; unsigned int
0x14005f504  mov     ecx, eax; int
0x14005f506  call    ?CitpLogFailureWorker@@YAXJPEBDI@Z; CitpLogFailureWorker(long,char const *,uint)
0x14005f50b  jmp     loc_14005F265
0x14005f510  mov     edi, 0C00000BBh
0x14005f515  jmp     loc_14005F379
0x1402397b6  push    rbp
0x1402397b8  sub     rsp, 30h
0x1402397bc  mov     rbp, rdx
0x1402397bf  mov     eax, 1
0x1402397c4  add     rsp, 30h
0x1402397c8  pop     rbp
0x1402397c9  retn
```
