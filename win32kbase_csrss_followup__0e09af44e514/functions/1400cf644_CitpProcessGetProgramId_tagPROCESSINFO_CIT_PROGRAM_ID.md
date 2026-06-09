# CitpProcessGetProgramId(tagPROCESSINFO *,_CIT_PROGRAM_ID *)

- ea: `0x1400cf644`
- end: `0x1400cf9ba`
- name: `?CitpProcessGetProgramId@@YAJPEAUtagPROCESSINFO@@PEAU_CIT_PROGRAM_ID@@@Z`
- size: `886`
- prototype: `int(struct tagPROCESSINFO *, struct _CIT_PROGRAM_ID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1400cef44`

## callees

- `0x14004a0d0`
- `0x14004d770`
- `0x1400cf644`
- `0x1400cfaa8`
- `0x1400cfb20`
- `0x1401afed4`
- `0x1401c47bc`
- `0x140238160`
- `0x140238800`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400cf6b5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400cf6b5`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1400cf69b`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1400cf69b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf839`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf839`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400cf8ad`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400cf8ad`
- `ntoskrnl!RtlImageNtHeader` at `0x1400cf76d`
- `ntoskrnl!RtlImageNtHeader` at `0x1400cf76d`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400cf821`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400cf821`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x1400cf8fb`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x1400cf8fb`
- `ntoskrnl!KeAttachProcess` at `0x1400cf6dd`
- `ntoskrnl!KeAttachProcess` at `0x1400cf6dd`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400cf715`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400cf715`
- `ntoskrnl!KeDetachProcess` at `0x1400cf85c`
- `ntoskrnl!KeDetachProcess` at `0x1400cf85c`

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
0x1400cf644  mov     [rsp+arg_10], rbx
0x1400cf649  mov     [rsp+arg_18], rsi
0x1400cf64e  push    rdi
0x1400cf64f  push    r12
0x1400cf651  push    r13
0x1400cf653  push    r14
0x1400cf655  push    r15
0x1400cf657  sub     rsp, 220h
0x1400cf65e  mov     rax, cs:__security_cookie
0x1400cf665  xor     rax, rsp
0x1400cf668  mov     [rsp+248h+var_38], rax
0x1400cf670  mov     r13, rdx
0x1400cf673  mov     r14, rcx
0x1400cf676  xor     ebx, ebx
0x1400cf678  mov     r12b, bl
0x1400cf67b  mov     [rsp+248h+var_218], bl
0x1400cf67f  mov     [rsp+248h+pImageFileName], rbx
0x1400cf684  mov     [rsp+248h+String], rbx
0x1400cf689  mov     esi, ebx
0x1400cf68b  mov     [rsp+248h+var_1E8], rbx
0x1400cf690  mov     r15d, ebx
0x1400cf693  mov     [rsp+248h+var_1E0], rbx
0x1400cf698  mov     rcx, [rcx]
0x1400cf69b  call    cs:__imp_PsGetProcessSectionBaseAddress
0x1400cf6a2  nop     dword ptr [rax+rax+00h]
0x1400cf6a7  mov     [rsp+248h+BaseAddress], rax
0x1400cf6ac  test    rax, rax
0x1400cf6af  jz      loc_1400CF98E
0x1400cf6b5  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400cf6bc  nop     dword ptr [rax+rax+00h]
0x1400cf6c1  mov     rdx, rax
0x1400cf6c4  test    rax, rax
0x1400cf6c7  jz      short loc_1400CF6D5
0x1400cf6c9  mov     rax, [rax]
0x1400cf6cc  neg     rax
0x1400cf6cf  sbb     rcx, rcx
0x1400cf6d2  and     rdx, rcx
0x1400cf6d5  cmp     r14, rdx
0x1400cf6d8  jz      short loc_1400CF6F1
0x1400cf6da  mov     rcx, [r14]; Process
0x1400cf6dd  call    cs:__imp_KeAttachProcess
0x1400cf6e4  nop     dword ptr [rax+rax+00h]
0x1400cf6e9  mov     r12b, 1
0x1400cf6ec  mov     [rsp+248h+var_218], r12b
0x1400cf6f1  mov     eax, [r14+328h]
0x1400cf6f8  shr     al, 4
0x1400cf6fb  and     al, 3
0x1400cf6fd  cmp     al, 1
0x1400cf6ff  jz      loc_1400CF8AA
0x1400cf705  mov     rdi, rbx
0x1400cf708  test    rdi, rdi
0x1400cf70b  jnz     short loc_1400CF768
0x1400cf70d  lea     rdx, [rsp+248h+pImageFileName]; pImageFileName
0x1400cf712  mov     rcx, [r14]; Process
0x1400cf715  call    cs:__imp_SeLocateProcessImageName
0x1400cf71c  nop     dword ptr [rax+rax+00h]
0x1400cf721  mov     edi, eax
0x1400cf723  test    eax, eax
0x1400cf725  js      loc_1400CF898
0x1400cf72b  mov     rax, [rsp+248h+pImageFileName]
0x1400cf730  movzx   ecx, word ptr [rax]
0x1400cf733  test    cx, cx
0x1400cf736  jz      loc_1400CF9B0
0x1400cf73c  mov     r8d, ecx
0x1400cf73f  shr     r8, 1; unsigned __int64
0x1400cf742  mov     rdx, rax
0x1400cf745  mov     rdx, [rax+8]; unsigned __int16 *
0x1400cf749  lea     rcx, [rsp+248h+String]; unsigned __int16 **
0x1400cf74e  call    ?CitpStringDuplicate@@YAJPEAPEAGPEBG_K@Z; CitpStringDuplicate(ushort * *,ushort const *,unsigned __int64)
0x1400cf753  mov     edi, eax
0x1400cf755  test    eax, eax
0x1400cf757  js      loc_1400CF819
0x1400cf75d  mov     rcx, [rsp+248h+String]; String
0x1400cf762  call    _wcsupr
0x1400cf767  nop
0x1400cf768  mov     rcx, [rsp+248h+BaseAddress]; BaseAddress
0x1400cf76d  call    cs:__imp_RtlImageNtHeader
0x1400cf774  nop     dword ptr [rax+rax+00h]
0x1400cf779  mov     edi, [rax+8]
0x1400cf77c  mov     [rsp+248h+var_1D8], edi
0x1400cf780  mov     eax, [rax+58h]
0x1400cf783  mov     dword ptr [rsp+248h+BaseAddress], eax
0x1400cf787  mov     [rsp+248h+var_1D4], eax
0x1400cf78b  jmp     short loc_1400CF7B7
0x1400cf78d  mov     edi, eax
0x1400cf78f  mov     eax, 0C0000001h
0x1400cf794  test    edi, edi
0x1400cf796  cmovns  edi, eax
0x1400cf799  mov     r8d, 753h; unsigned int
0x1400cf79f  mov     ecx, edi; int
0x1400cf7a1  call    ?CitpLogFailureWorker@@YAXJPEBDI@Z; CitpLogFailureWorker(long,char const *,uint)
0x1400cf7a6  mov     r12b, [rsp+248h+var_218]
0x1400cf7ab  mov     rsi, [rsp+248h+var_1E8]
0x1400cf7b0  mov     r15, [rsp+248h+var_1E0]
0x1400cf7b5  jmp     short loc_1400CF819
0x1400cf7b7  test    rsi, rsi
0x1400cf7ba  jz      short loc_1400CF7C4
0x1400cf7bc  mov     rcx, rsi; String
0x1400cf7bf  call    _wcsupr
0x1400cf7c4  mov     rax, [rsp+248h+String]
0x1400cf7c9  mov     [r13+0], rax
0x1400cf7cd  mov     [rsp+248h+String], rbx
0x1400cf7d2  mov     [r13+8], rsi
0x1400cf7d6  mov     rsi, rbx
0x1400cf7d9  mov     [r13+18h], edi
0x1400cf7dd  mov     eax, dword ptr [rsp+248h+BaseAddress]
0x1400cf7e1  mov     [r13+1Ch], eax
0x1400cf7e5  mov     eax, [r14+328h]
0x1400cf7ec  shr     rax, 4
0x1400cf7f0  and     eax, 3
0x1400cf7f3  mov     [r13+20h], eax
0x1400cf7f7  mov     rcx, r13; struct _CIT_PROGRAM_ID *
0x1400cf7fa  call    ?CitpProgramIdCalculateHash@@YA_KPEBU_CIT_PROGRAM_ID@@@Z; CitpProgramIdCalculateHash(_CIT_PROGRAM_ID const *)
0x1400cf7ff  mov     [r13+10h], rax
0x1400cf803  mov     edi, ebx
0x1400cf805  jmp     short loc_1400CF819
0x1400cf807  mov     edi, 0C000009Ah
0x1400cf80c  mov     r8d, 70Eh; unsigned int
0x1400cf812  mov     ecx, edi; int
0x1400cf814  call    ?CitpLogFailureWorker@@YAXJPEBDI@Z; CitpLogFailureWorker(long,char const *,uint)
0x1400cf819  test    r15, r15
0x1400cf81c  jz      short loc_1400CF82D
0x1400cf81e  mov     rcx, r15; PrimaryToken
0x1400cf821  call    cs:__imp_PsDereferencePrimaryToken
0x1400cf828  nop     dword ptr [rax+rax+00h]
0x1400cf82d  mov     rcx, [rsp+248h+pImageFileName]; P
0x1400cf832  test    rcx, rcx
0x1400cf835  jz      short loc_1400CF845
0x1400cf837  xor     edx, edx; Tag
0x1400cf839  call    cs:__imp_ExFreePoolWithTag
0x1400cf840  nop     dword ptr [rax+rax+00h]
0x1400cf845  mov     rcx, [rsp+248h+String]; Buffer
0x1400cf84a  call    GreDeleteFastMutex
0x1400cf84f  mov     rcx, rsi; Buffer
0x1400cf852  call    GreDeleteFastMutex
0x1400cf857  test    r12b, r12b
0x1400cf85a  jz      short loc_1400CF868
0x1400cf85c  call    cs:__imp_KeDetachProcess
0x1400cf863  nop     dword ptr [rax+rax+00h]
0x1400cf868  mov     eax, edi
0x1400cf86a  mov     rcx, [rsp+248h+var_38]
0x1400cf872  xor     rcx, rsp; StackCookie
0x1400cf875  call    __security_check_cookie
0x1400cf87a  lea     r11, [rsp+248h+var_28]
0x1400cf882  mov     rbx, [r11+40h]
0x1400cf886  mov     rsi, [r11+48h]
0x1400cf88a  mov     rsp, r11
0x1400cf88d  pop     r15
0x1400cf88f  pop     r14
0x1400cf891  pop     r13
0x1400cf893  pop     r12
0x1400cf895  pop     rdi
0x1400cf896  retn
0x1400cf898  mov     [rsp+248h+pImageFileName], rbx
0x1400cf89d  mov     r8d, 726h
0x1400cf8a3  mov     ecx, eax
0x1400cf8a5  jmp     loc_1400CF814
0x1400cf8aa  mov     rcx, [r14]; Process
0x1400cf8ad  call    cs:__imp_PsReferencePrimaryToken
0x1400cf8b4  nop     dword ptr [rax+rax+00h]
0x1400cf8b9  mov     r15, rax
0x1400cf8bc  mov     [rsp+248h+var_1E0], rax
0x1400cf8c1  mov     edi, 100h
0x1400cf8c6  mov     [rsp+248h+Size], rdi
0x1400cf8cb  mov     [rsp+248h+var_1F0], 82h
0x1400cf8d4  mov     [rsp+248h+var_220], rbx
0x1400cf8d9  lea     rax, [rsp+248h+var_1F0]
0x1400cf8de  mov     [rsp+248h+var_228], rax
0x1400cf8e3  lea     r9, [rsp+248h+var_1C8]
0x1400cf8eb  lea     r8, [rsp+248h+Size]
0x1400cf8f0  lea     rdx, [rsp+248h+Src]
0x1400cf8f8  mov     rcx, r15
0x1400cf8fb  call    cs:__imp_RtlQueryPackageIdentity
0x1400cf902  nop     dword ptr [rax+rax+00h]
0x1400cf907  test    eax, eax
0x1400cf909  js      loc_1400CF99E
0x1400cf90f  mov     esi, 49637355h
0x1400cf914  mov     r8d, esi; unsigned int
0x1400cf917  mov     rdx, [rsp+248h+Size]; unsigned __int64
0x1400cf91c  mov     ecx, edi; unsigned __int64
0x1400cf91e  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400cf923  mov     rdi, rax
0x1400cf926  mov     [rsp+248h+String], rax
0x1400cf92b  mov     r8d, esi; unsigned int
0x1400cf92e  mov     rdx, [rsp+248h+var_1F0]; unsigned __int64
0x1400cf933  mov     ecx, 100h; unsigned __int64
0x1400cf938  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400cf93d  mov     rsi, rax
0x1400cf940  mov     [rsp+248h+var_1E8], rax
0x1400cf945  test    rdi, rdi
0x1400cf948  jz      loc_1400CF807
0x1400cf94e  test    rax, rax
0x1400cf951  jz      loc_1400CF807
0x1400cf957  mov     r8, [rsp+248h+Size]; Size
0x1400cf95c  lea     rdx, [rsp+248h+Src]; Src
0x1400cf964  mov     rcx, rdi; void *
0x1400cf967  call    memmove
0x1400cf96c  mov     rcx, rdi; String
0x1400cf96f  call    _wcsupr
0x1400cf974  mov     r8, [rsp+248h+var_1F0]; Size
0x1400cf979  lea     rdx, [rsp+248h+var_1C8]; Src
0x1400cf981  mov     rcx, rsi; void *
0x1400cf984  call    memmove
0x1400cf989  jmp     loc_1400CF708
0x1400cf98e  mov     edi, 0C00000BBh
0x1400cf993  mov     r8d, 6E4h
0x1400cf999  jmp     loc_1400CF812
0x1400cf99e  mov     r8d, 719h; unsigned int
0x1400cf9a4  mov     ecx, eax; int
0x1400cf9a6  call    ?CitpLogFailureWorker@@YAXJPEBDI@Z; CitpLogFailureWorker(long,char const *,uint)
0x1400cf9ab  jmp     loc_1400CF705
0x1400cf9b0  mov     edi, 0C00000BBh
0x1400cf9b5  jmp     loc_1400CF819
0x140239102  push    rbp
0x140239104  sub     rsp, 30h
0x140239108  mov     rbp, rdx
0x14023910b  mov     eax, 1
0x140239110  add     rsp, 30h
0x140239114  pop     rbp
0x140239115  retn
```
