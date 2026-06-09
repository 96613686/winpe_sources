# CitpProcessGetProgramId(tagPROCESSINFO *,_CIT_PROGRAM_ID *)

- ea: `0x1400c2454`
- end: `0x1400c27ca`
- name: `?CitpProcessGetProgramId@@YAJPEAUtagPROCESSINFO@@PEAU_CIT_PROGRAM_ID@@@Z`
- size: `886`
- prototype: `__int64 __fastcall(PRKPROCESS *, struct _CIT_PROGRAM_ID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1400c1b64`

## callees

- `0x14007b930`
- `0x14007efd0`
- `0x1400c2454`
- `0x1400c28b8`
- `0x1400c2930`
- `0x1401b10e8`
- `0x1401c58ec`
- `0x1402388e0`
- `0x140238f80`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400c24c5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400c24c5`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1400c24ab`
- `ntoskrnl!PsGetProcessSectionBaseAddress` at `0x1400c24ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2649`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2649`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400c26bd`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400c26bd`
- `ntoskrnl!RtlImageNtHeader` at `0x1400c257d`
- `ntoskrnl!RtlImageNtHeader` at `0x1400c257d`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400c2631`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400c2631`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x1400c270b`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x1400c270b`
- `ntoskrnl!KeAttachProcess` at `0x1400c24ed`
- `ntoskrnl!KeAttachProcess` at `0x1400c24ed`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400c2525`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400c2525`
- `ntoskrnl!KeDetachProcess` at `0x1400c266c`
- `ntoskrnl!KeDetachProcess` at `0x1400c266c`

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
0x1400c2454  mov     [rsp+arg_10], rbx
0x1400c2459  mov     [rsp+arg_18], rsi
0x1400c245e  push    rdi
0x1400c245f  push    r12
0x1400c2461  push    r13
0x1400c2463  push    r14
0x1400c2465  push    r15
0x1400c2467  sub     rsp, 220h
0x1400c246e  mov     rax, cs:__security_cookie
0x1400c2475  xor     rax, rsp
0x1400c2478  mov     [rsp+248h+var_38], rax
0x1400c2480  mov     r13, rdx
0x1400c2483  mov     r14, rcx
0x1400c2486  xor     ebx, ebx
0x1400c2488  mov     r12b, bl
0x1400c248b  mov     [rsp+248h+var_218], bl
0x1400c248f  mov     [rsp+248h+pImageFileName], rbx
0x1400c2494  mov     [rsp+248h+String], rbx
0x1400c2499  mov     esi, ebx
0x1400c249b  mov     [rsp+248h+var_1E8], rbx
0x1400c24a0  mov     r15d, ebx
0x1400c24a3  mov     [rsp+248h+var_1E0], rbx
0x1400c24a8  mov     rcx, [rcx]
0x1400c24ab  call    cs:__imp_PsGetProcessSectionBaseAddress
0x1400c24b2  nop     dword ptr [rax+rax+00h]
0x1400c24b7  mov     [rsp+248h+BaseAddress], rax
0x1400c24bc  test    rax, rax
0x1400c24bf  jz      loc_1400C279E
0x1400c24c5  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400c24cc  nop     dword ptr [rax+rax+00h]
0x1400c24d1  mov     rdx, rax
0x1400c24d4  test    rax, rax
0x1400c24d7  jz      short loc_1400C24E5
0x1400c24d9  mov     rax, [rax]
0x1400c24dc  neg     rax
0x1400c24df  sbb     rcx, rcx
0x1400c24e2  and     rdx, rcx
0x1400c24e5  cmp     r14, rdx
0x1400c24e8  jz      short loc_1400C2501
0x1400c24ea  mov     rcx, [r14]; Process
0x1400c24ed  call    cs:__imp_KeAttachProcess
0x1400c24f4  nop     dword ptr [rax+rax+00h]
0x1400c24f9  mov     r12b, 1
0x1400c24fc  mov     [rsp+248h+var_218], r12b
0x1400c2501  mov     eax, [r14+328h]
0x1400c2508  shr     al, 4
0x1400c250b  and     al, 3
0x1400c250d  cmp     al, 1
0x1400c250f  jz      loc_1400C26BA
0x1400c2515  mov     rdi, rbx
0x1400c2518  test    rdi, rdi
0x1400c251b  jnz     short loc_1400C2578
0x1400c251d  lea     rdx, [rsp+248h+pImageFileName]; pImageFileName
0x1400c2522  mov     rcx, [r14]; Process
0x1400c2525  call    cs:__imp_SeLocateProcessImageName
0x1400c252c  nop     dword ptr [rax+rax+00h]
0x1400c2531  mov     edi, eax
0x1400c2533  test    eax, eax
0x1400c2535  js      loc_1400C26A8
0x1400c253b  mov     rax, [rsp+248h+pImageFileName]
0x1400c2540  movzx   ecx, word ptr [rax]
0x1400c2543  test    cx, cx
0x1400c2546  jz      loc_1400C27C0
0x1400c254c  mov     r8d, ecx
0x1400c254f  shr     r8, 1; unsigned __int64
0x1400c2552  mov     rdx, rax
0x1400c2555  mov     rdx, [rax+8]; unsigned __int16 *
0x1400c2559  lea     rcx, [rsp+248h+String]; unsigned __int16 **
0x1400c255e  call    ?CitpStringDuplicate@@YAJPEAPEAGPEBG_K@Z; CitpStringDuplicate(ushort * *,ushort const *,unsigned __int64)
0x1400c2563  mov     edi, eax
0x1400c2565  test    eax, eax
0x1400c2567  js      loc_1400C2629
0x1400c256d  mov     rcx, [rsp+248h+String]; String
0x1400c2572  call    _wcsupr
0x1400c2577  nop
0x1400c2578  mov     rcx, [rsp+248h+BaseAddress]; BaseAddress
0x1400c257d  call    cs:__imp_RtlImageNtHeader
0x1400c2584  nop     dword ptr [rax+rax+00h]
0x1400c2589  mov     edi, [rax+8]
0x1400c258c  mov     [rsp+248h+var_1D8], edi
0x1400c2590  mov     eax, [rax+58h]
0x1400c2593  mov     dword ptr [rsp+248h+BaseAddress], eax
0x1400c2597  mov     [rsp+248h+var_1D4], eax
0x1400c259b  jmp     short loc_1400C25C7
0x1400c259d  mov     edi, eax
0x1400c259f  mov     eax, 0C0000001h
0x1400c25a4  test    edi, edi
0x1400c25a6  cmovns  edi, eax
0x1400c25a9  mov     r8d, 753h; unsigned int
0x1400c25af  mov     ecx, edi; int
0x1400c25b1  call    ?CitpLogFailureWorker@@YAXJPEBDI@Z; CitpLogFailureWorker(long,char const *,uint)
0x1400c25b6  mov     r12b, [rsp+248h+var_218]
0x1400c25bb  mov     rsi, [rsp+248h+var_1E8]
0x1400c25c0  mov     r15, [rsp+248h+var_1E0]
0x1400c25c5  jmp     short loc_1400C2629
0x1400c25c7  test    rsi, rsi
0x1400c25ca  jz      short loc_1400C25D4
0x1400c25cc  mov     rcx, rsi; String
0x1400c25cf  call    _wcsupr
0x1400c25d4  mov     rax, [rsp+248h+String]
0x1400c25d9  mov     [r13+0], rax
0x1400c25dd  mov     [rsp+248h+String], rbx
0x1400c25e2  mov     [r13+8], rsi
0x1400c25e6  mov     rsi, rbx
0x1400c25e9  mov     [r13+18h], edi
0x1400c25ed  mov     eax, dword ptr [rsp+248h+BaseAddress]
0x1400c25f1  mov     [r13+1Ch], eax
0x1400c25f5  mov     eax, [r14+328h]
0x1400c25fc  shr     rax, 4
0x1400c2600  and     eax, 3
0x1400c2603  mov     [r13+20h], eax
0x1400c2607  mov     rcx, r13; struct _CIT_PROGRAM_ID *
0x1400c260a  call    ?CitpProgramIdCalculateHash@@YA_KPEBU_CIT_PROGRAM_ID@@@Z; CitpProgramIdCalculateHash(_CIT_PROGRAM_ID const *)
0x1400c260f  mov     [r13+10h], rax
0x1400c2613  mov     edi, ebx
0x1400c2615  jmp     short loc_1400C2629
0x1400c2617  mov     edi, 0C000009Ah
0x1400c261c  mov     r8d, 70Eh; unsigned int
0x1400c2622  mov     ecx, edi; int
0x1400c2624  call    ?CitpLogFailureWorker@@YAXJPEBDI@Z; CitpLogFailureWorker(long,char const *,uint)
0x1400c2629  test    r15, r15
0x1400c262c  jz      short loc_1400C263D
0x1400c262e  mov     rcx, r15; PrimaryToken
0x1400c2631  call    cs:__imp_PsDereferencePrimaryToken
0x1400c2638  nop     dword ptr [rax+rax+00h]
0x1400c263d  mov     rcx, [rsp+248h+pImageFileName]; P
0x1400c2642  test    rcx, rcx
0x1400c2645  jz      short loc_1400C2655
0x1400c2647  xor     edx, edx; Tag
0x1400c2649  call    cs:__imp_ExFreePoolWithTag
0x1400c2650  nop     dword ptr [rax+rax+00h]
0x1400c2655  mov     rcx, [rsp+248h+String]; Buffer
0x1400c265a  call    GreDeleteFastMutex
0x1400c265f  mov     rcx, rsi; Buffer
0x1400c2662  call    GreDeleteFastMutex
0x1400c2667  test    r12b, r12b
0x1400c266a  jz      short loc_1400C2678
0x1400c266c  call    cs:__imp_KeDetachProcess
0x1400c2673  nop     dword ptr [rax+rax+00h]
0x1400c2678  mov     eax, edi
0x1400c267a  mov     rcx, [rsp+248h+var_38]
0x1400c2682  xor     rcx, rsp; StackCookie
0x1400c2685  call    __security_check_cookie
0x1400c268a  lea     r11, [rsp+248h+var_28]
0x1400c2692  mov     rbx, [r11+40h]
0x1400c2696  mov     rsi, [r11+48h]
0x1400c269a  mov     rsp, r11
0x1400c269d  pop     r15
0x1400c269f  pop     r14
0x1400c26a1  pop     r13
0x1400c26a3  pop     r12
0x1400c26a5  pop     rdi
0x1400c26a6  retn
0x1400c26a8  mov     [rsp+248h+pImageFileName], rbx
0x1400c26ad  mov     r8d, 726h
0x1400c26b3  mov     ecx, eax
0x1400c26b5  jmp     loc_1400C2624
0x1400c26ba  mov     rcx, [r14]; Process
0x1400c26bd  call    cs:__imp_PsReferencePrimaryToken
0x1400c26c4  nop     dword ptr [rax+rax+00h]
0x1400c26c9  mov     r15, rax
0x1400c26cc  mov     [rsp+248h+var_1E0], rax
0x1400c26d1  mov     edi, 100h
0x1400c26d6  mov     [rsp+248h+Size], rdi
0x1400c26db  mov     [rsp+248h+var_1F0], 82h
0x1400c26e4  mov     [rsp+248h+var_220], rbx
0x1400c26e9  lea     rax, [rsp+248h+var_1F0]
0x1400c26ee  mov     [rsp+248h+var_228], rax
0x1400c26f3  lea     r9, [rsp+248h+var_1C8]
0x1400c26fb  lea     r8, [rsp+248h+Size]
0x1400c2700  lea     rdx, [rsp+248h+Src]
0x1400c2708  mov     rcx, r15
0x1400c270b  call    cs:__imp_RtlQueryPackageIdentity
0x1400c2712  nop     dword ptr [rax+rax+00h]
0x1400c2717  test    eax, eax
0x1400c2719  js      loc_1400C27AE
0x1400c271f  mov     esi, 49637355h
0x1400c2724  mov     r8d, esi; unsigned int
0x1400c2727  mov     rdx, [rsp+248h+Size]; unsigned __int64
0x1400c272c  mov     ecx, edi; unsigned __int64
0x1400c272e  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400c2733  mov     rdi, rax
0x1400c2736  mov     [rsp+248h+String], rax
0x1400c273b  mov     r8d, esi; unsigned int
0x1400c273e  mov     rdx, [rsp+248h+var_1F0]; unsigned __int64
0x1400c2743  mov     ecx, 100h; unsigned __int64
0x1400c2748  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400c274d  mov     rsi, rax
0x1400c2750  mov     [rsp+248h+var_1E8], rax
0x1400c2755  test    rdi, rdi
0x1400c2758  jz      loc_1400C2617
0x1400c275e  test    rax, rax
0x1400c2761  jz      loc_1400C2617
0x1400c2767  mov     r8, [rsp+248h+Size]; Size
0x1400c276c  lea     rdx, [rsp+248h+Src]; Src
0x1400c2774  mov     rcx, rdi; void *
0x1400c2777  call    memmove
0x1400c277c  mov     rcx, rdi; String
0x1400c277f  call    _wcsupr
0x1400c2784  mov     r8, [rsp+248h+var_1F0]; Size
0x1400c2789  lea     rdx, [rsp+248h+var_1C8]; Src
0x1400c2791  mov     rcx, rsi; void *
0x1400c2794  call    memmove
0x1400c2799  jmp     loc_1400C2518
0x1400c279e  mov     edi, 0C00000BBh
0x1400c27a3  mov     r8d, 6E4h
0x1400c27a9  jmp     loc_1400C2622
0x1400c27ae  mov     r8d, 719h; unsigned int
0x1400c27b4  mov     ecx, eax; int
0x1400c27b6  call    ?CitpLogFailureWorker@@YAXJPEBDI@Z; CitpLogFailureWorker(long,char const *,uint)
0x1400c27bb  jmp     loc_1400C2515
0x1400c27c0  mov     edi, 0C00000BBh
0x1400c27c5  jmp     loc_1400C2629
0x1402396e6  push    rbp
0x1402396e8  sub     rsp, 30h
0x1402396ec  mov     rbp, rdx
0x1402396ef  mov     eax, 1
0x1402396f4  add     rsp, 30h
0x1402396f8  pop     rbp
0x1402396f9  retn
```
