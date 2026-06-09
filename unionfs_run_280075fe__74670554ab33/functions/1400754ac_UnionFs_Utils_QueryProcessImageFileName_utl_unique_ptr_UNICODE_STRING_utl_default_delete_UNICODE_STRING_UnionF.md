# UnionFs::Utils::QueryProcessImageFileName(utl::unique_ptr<_UNICODE_STRING,utl::default_delete<_UNICODE_STRING>> &,UnionFs::StackEventTracer &,_KPROCESS *)

- ea: `0x1400754ac`
- end: `0x140075794`
- name: `?QueryProcessImageFileName@Utils@UnionFs@@YAJAEAV?$unique_ptr@U_UNICODE_STRING@@U?$default_delete@U_UNICODE_STRING@@@utl@@@utl@@AEAVStackEventTracer@2@PEAU_KPROCESS@@@Z`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14006f51c`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x1400754ac`

## import_xrefs

- `ntoskrnl!ZwQueryInformationProcess` at `0x140075598`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140075598`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400754ea`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400754ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400754de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075600`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400756bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075701`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075755`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400754de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075600`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400756bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075701`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075755`
- `ntoskrnl!ExAllocatePool2` at `0x1400755e2`
- `ntoskrnl!ExAllocatePool2` at `0x1400755e2`
- `ntoskrnl!ZwClose` at `0x14007555d`
- `ntoskrnl!ZwClose` at `0x1400756d4`
- `ntoskrnl!ZwClose` at `0x140075716`
- `ntoskrnl!ZwClose` at `0x14007576a`
- `ntoskrnl!ZwClose` at `0x14007555d`
- `ntoskrnl!ZwClose` at `0x1400756d4`
- `ntoskrnl!ZwClose` at `0x140075716`
- `ntoskrnl!ZwClose` at `0x14007576a`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14007551b`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14007551b`

## string_xrefs

- `0x14007552d`: `API: Opening process handle`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::QueryProcessImageFileName(void **a1, int a2, __int64 a3)
{
  void *v4; // rcx
  PEPROCESS CurrentProcess; // rax
  NTSTATUS v7; // ebx
  _WORD *v9; // rbx
  ULONG v10; // r9d
  int i; // r15d
  NTSTATUS InformationProcess; // edi
  __int64 v13; // rdx
  __int64 Pool2; // rax
  void *v15; // rcx
  __int64 v16; // r8
  void *v17; // rcx
  const char *AccessMode; // [rsp+28h] [rbp-18h]
  HANDLE ProcessHandle; // [rsp+80h] [rbp+40h] BYREF
  __int64 ReturnLength; // [rsp+90h] [rbp+50h] BYREF

  ReturnLength = a3;
  v4 = *a1;
  *a1 = 0;
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  CurrentProcess = IoGetCurrentProcess();
  ProcessHandle = 0;
  v7 = ObOpenObjectByPointer(CurrentProcess, 0x200u, 0, 0, 0, 0, &ProcessHandle);
  if ( v7 >= 0 )
  {
    v9 = 0;
    LODWORD(ReturnLength) = 0;
    v10 = 0;
    for ( i = 0; ; i = 1 )
    {
      InformationProcess = ZwQueryInformationProcess(
                             ProcessHandle,
                             ProcessImageFileName,
                             v9,
                             v10,
                             (PULONG)&ReturnLength);
      if ( i )
        break;
      if ( (int)(InformationProcess + 0x80000000) >= 0 && InformationProcess != -1073741820 )
      {
        v16 = 0x4E30021242ALL;
LABEL_24:
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)InformationProcess,
          a2,
          (struct UnionFs::StackEventTracer *)v16,
          (unsigned __int64)"UnionFs::Utils::QueryProcessImageFileName",
          "API: Querying process image file name",
          AccessMode);
        goto LABEL_25;
      }
      if ( (unsigned int)ReturnLength < 0x10 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0000001LL,
          a2,
          (struct UnionFs::StackEventTracer *)0x4E500212438LL,
          (unsigned __int64)"UnionFs::Utils::QueryProcessImageFileName",
          "ORIGIN: Invalid buffer size for process image file name",
          AccessMode);
        if ( v9 )
LABEL_38:
          ExFreePoolWithTag(v9, 0);
        if ( ProcessHandle )
          ZwClose(ProcessHandle);
        return 3221225473LL;
      }
      v13 = (unsigned int)ReturnLength;
      if ( !(_DWORD)ReturnLength )
        v13 = 1;
      Pool2 = ExAllocatePool2(256, v13, 1852261973);
      if ( !Pool2 )
      {
        InformationProcess = -1073741670;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          a2,
          (struct UnionFs::StackEventTracer *)0x4E600212441LL,
          (unsigned __int64)"UnionFs::Utils::QueryProcessImageFileName",
          "ORIGIN: Allocating image file name buffer",
          AccessMode);
LABEL_25:
        if ( v9 )
          ExFreePoolWithTag(v9, 0);
        if ( ProcessHandle )
          ZwClose(ProcessHandle);
        return (unsigned int)InformationProcess;
      }
      v15 = v9;
      v9 = (_WORD *)Pool2;
      if ( v15 )
        ExFreePoolWithTag(v15, 0);
      v10 = ReturnLength;
    }
    if ( InformationProcess < 0 )
    {
      v16 = 0x4E10021241ALL;
      goto LABEL_24;
    }
    if ( !*v9 || (*v9 & 1) != 0 )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000001LL,
        a2,
        (struct UnionFs::StackEventTracer *)0x4E200212421LL,
        (unsigned __int64)"UnionFs::Utils::QueryProcessImageFileName",
        "ORIGIN: Invalid image file name",
        AccessMode);
      goto LABEL_38;
    }
    v17 = *a1;
    *a1 = v9;
    if ( v17 )
      ExFreePoolWithTag(v17, 0);
    if ( ProcessHandle )
      ZwClose(ProcessHandle);
    return 0;
  }
  else
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v7,
      a2,
      (struct UnionFs::StackEventTracer *)0x4E000212408LL,
      (unsigned __int64)"UnionFs::Utils::QueryProcessImageFileName",
      "API: Opening process handle",
      AccessMode);
    if ( ProcessHandle )
      ZwClose(ProcessHandle);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x1400754ac  mov     [rsp-38h+arg_8], rbx
0x1400754b1  mov     [rsp-38h+ReturnLength], r8
0x1400754b6  push    rbp
0x1400754b7  push    rsi
0x1400754b8  push    rdi
0x1400754b9  push    r12
0x1400754bb  push    r13
0x1400754bd  push    r14
0x1400754bf  push    r15
0x1400754c1  mov     rbp, rsp
0x1400754c4  sub     rsp, 40h
0x1400754c8  mov     rsi, rcx
0x1400754cb  xor     r12d, r12d
0x1400754ce  mov     rcx, [rcx]; P
0x1400754d1  mov     r14, rdx
0x1400754d4  mov     [rsi], r12
0x1400754d7  test    rcx, rcx
0x1400754da  jz      short loc_1400754EA
0x1400754dc  xor     edx, edx; Tag
0x1400754de  call    cs:__imp_ExFreePoolWithTag
0x1400754e5  nop     dword ptr [rax+rax+00h]
0x1400754ea  call    cs:__imp_IoGetCurrentProcess
0x1400754f1  nop     dword ptr [rax+rax+00h]
0x1400754f6  lea     rcx, [rbp+ProcessHandle]
0x1400754fa  mov     [rbp+ProcessHandle], r12
0x1400754fe  mov     [rsp+40h+Handle], rcx; Handle
0x140075503  xor     r9d, r9d; DesiredAccess
0x140075506  mov     byte ptr [rsp+40h+AccessMode], r12b; char *
0x14007550b  mov     rcx, rax; Object
0x14007550e  xor     r8d, r8d; PassedAccessState
0x140075511  mov     [rsp+40h+ObjectType], r12; ObjectType
0x140075516  mov     edx, 200h; HandleAttributes
0x14007551b  call    cs:__imp_ObOpenObjectByPointer
0x140075522  nop     dword ptr [rax+rax+00h]
0x140075527  mov     ebx, eax
0x140075529  test    eax, eax
0x14007552b  jns     short loc_140075570
0x14007552d  lea     rax, aApiOpeningProc; "API: Opening process handle"
0x140075534  mov     r8, 4E000212408h; struct UnionFs::StackEventTracer *
0x14007553e  lea     r9, aUnionfsUtilsQu_1; "UnionFs::Utils::QueryProcessImageFileNa"...
0x140075545  mov     [rsp+40h+ObjectType], rax; char *
0x14007554a  mov     rdx, r14; int
0x14007554d  mov     ecx, ebx; this
0x14007554f  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075554  mov     rcx, [rbp+ProcessHandle]; Handle
0x140075558  test    rcx, rcx
0x14007555b  jz      short loc_140075569
0x14007555d  call    cs:__imp_ZwClose
0x140075564  nop     dword ptr [rax+rax+00h]
0x140075569  mov     eax, ebx
0x14007556b  jmp     loc_14007577B
0x140075570  mov     rbx, r12
0x140075573  mov     dword ptr [rbp+ReturnLength], r12d
0x140075577  mov     r9d, r12d; ProcessInformationLength
0x14007557a  mov     r15d, r12d
0x14007557d  mov     r13d, 1
0x140075583  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x140075587  lea     rax, [rbp+ReturnLength]
0x14007558b  mov     r8, rbx; ProcessInformation
0x14007558e  mov     [rsp+40h+ObjectType], rax; ReturnLength
0x140075593  mov     edx, 1Bh; ProcessInformationClass
0x140075598  call    cs:__imp_ZwQueryInformationProcess
0x14007559f  nop     dword ptr [rax+rax+00h]
0x1400755a4  mov     edi, eax
0x1400755a6  test    r15d, r15d
0x1400755a9  jnz     loc_14007568A
0x1400755af  mov     eax, 80000000h
0x1400755b4  lea     ecx, [rdi+rax]
0x1400755b7  test    eax, ecx
0x1400755b9  jnz     short loc_1400755C3
0x1400755bb  cmp     edi, 0C0000004h
0x1400755c1  jnz     short loc_140075618
0x1400755c3  cmp     dword ptr [rbp+ReturnLength], 10h
0x1400755c7  jb      loc_140075652
0x1400755cd  mov     edx, dword ptr [rbp+ReturnLength]
0x1400755d0  mov     ecx, 100h
0x1400755d5  test    rdx, rdx
0x1400755d8  mov     r8d, 6E674655h
0x1400755de  cmovz   rdx, r13
0x1400755e2  call    cs:__imp_ExAllocatePool2
0x1400755e9  nop     dword ptr [rax+rax+00h]
0x1400755ee  test    rax, rax
0x1400755f1  jz      short loc_140075624
0x1400755f3  mov     rcx, rbx; P
0x1400755f6  mov     rbx, rax
0x1400755f9  test    rcx, rcx
0x1400755fc  jz      short loc_14007560C
0x1400755fe  xor     edx, edx; Tag
0x140075600  call    cs:__imp_ExFreePoolWithTag
0x140075607  nop     dword ptr [rax+rax+00h]
0x14007560c  mov     r9d, dword ptr [rbp+ReturnLength]
0x140075610  mov     r15d, r13d
0x140075613  jmp     loc_140075583
0x140075618  mov     r8, 4E30021242Ah
0x140075622  jmp     short loc_140075698
0x140075624  lea     rax, aOriginAllocati_27; "ORIGIN: Allocating image file name buff"...
0x14007562b  mov     edi, 0C000009Ah
0x140075630  mov     ecx, edi; this
0x140075632  mov     [rsp+40h+ObjectType], rax; char *
0x140075637  lea     r9, aUnionfsUtilsQu_1; "UnionFs::Utils::QueryProcessImageFileNa"...
0x14007563e  mov     r8, 4E600212441h; struct UnionFs::StackEventTracer *
0x140075648  mov     rdx, r14; int
0x14007564b  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075650  jmp     short loc_1400756B5
0x140075652  lea     rax, aOriginInvalidB; "ORIGIN: Invalid buffer size for process"...
0x140075659  mov     r8, 4E500212438h; struct UnionFs::StackEventTracer *
0x140075663  lea     r9, aUnionfsUtilsQu_1; "UnionFs::Utils::QueryProcessImageFileNa"...
0x14007566a  mov     [rsp+40h+ObjectType], rax; char *
0x14007566f  mov     rdx, r14; int
0x140075672  mov     ecx, 0C0000001h; this
0x140075677  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007567c  test    rbx, rbx
0x14007567f  jz      loc_140075761
0x140075685  jmp     loc_140075750
0x14007568a  test    edi, edi
0x14007568c  jns     short loc_1400756E7
0x14007568e  mov     r8, 4E10021241Ah; struct UnionFs::StackEventTracer *
0x140075698  lea     rax, aApiQueryingPro; "API: Querying process image file name"
0x14007569f  mov     rdx, r14; int
0x1400756a2  lea     r9, aUnionfsUtilsQu_1; "UnionFs::Utils::QueryProcessImageFileNa"...
0x1400756a9  mov     [rsp+40h+ObjectType], rax; char *
0x1400756ae  mov     ecx, edi; this
0x1400756b0  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400756b5  test    rbx, rbx
0x1400756b8  jz      short loc_1400756CB
0x1400756ba  xor     edx, edx; Tag
0x1400756bc  mov     rcx, rbx; P
0x1400756bf  call    cs:__imp_ExFreePoolWithTag
0x1400756c6  nop     dword ptr [rax+rax+00h]
0x1400756cb  mov     rcx, [rbp+ProcessHandle]; Handle
0x1400756cf  test    rcx, rcx
0x1400756d2  jz      short loc_1400756E0
0x1400756d4  call    cs:__imp_ZwClose
0x1400756db  nop     dword ptr [rax+rax+00h]
0x1400756e0  mov     eax, edi
0x1400756e2  jmp     loc_14007577B
0x1400756e7  movzx   eax, word ptr [rbx]
0x1400756ea  test    ax, ax
0x1400756ed  jz      short loc_140075726
0x1400756ef  test    r13b, al
0x1400756f2  jnz     short loc_140075726
0x1400756f4  mov     rcx, [rsi]; P
0x1400756f7  mov     [rsi], rbx
0x1400756fa  test    rcx, rcx
0x1400756fd  jz      short loc_14007570D
0x1400756ff  xor     edx, edx; Tag
0x140075701  call    cs:__imp_ExFreePoolWithTag
0x140075708  nop     dword ptr [rax+rax+00h]
0x14007570d  mov     rcx, [rbp+ProcessHandle]; Handle
0x140075711  test    rcx, rcx
0x140075714  jz      short loc_140075722
0x140075716  call    cs:__imp_ZwClose
0x14007571d  nop     dword ptr [rax+rax+00h]
0x140075722  xor     eax, eax
0x140075724  jmp     short loc_14007577B
0x140075726  lea     rax, aOriginInvalidI; "ORIGIN: Invalid image file name"
0x14007572d  mov     r8, 4E200212421h; struct UnionFs::StackEventTracer *
0x140075737  lea     r9, aUnionfsUtilsQu_1; "UnionFs::Utils::QueryProcessImageFileNa"...
0x14007573e  mov     [rsp+40h+ObjectType], rax; char *
0x140075743  mov     rdx, r14; int
0x140075746  mov     ecx, 0C0000001h; this
0x14007574b  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075750  xor     edx, edx; Tag
0x140075752  mov     rcx, rbx; P
0x140075755  call    cs:__imp_ExFreePoolWithTag
0x14007575c  nop     dword ptr [rax+rax+00h]
0x140075761  mov     rcx, [rbp+ProcessHandle]; Handle
0x140075765  test    rcx, rcx
0x140075768  jz      short loc_140075776
0x14007576a  call    cs:__imp_ZwClose
0x140075771  nop     dword ptr [rax+rax+00h]
0x140075776  mov     eax, 0C0000001h
0x14007577b  mov     rbx, [rsp+40h+arg_8]
0x140075783  add     rsp, 40h
0x140075787  pop     r15
0x140075789  pop     r14
0x14007578b  pop     r13
0x14007578d  pop     r12
0x14007578f  pop     rdi
0x140075790  pop     rsi
0x140075791  pop     rbp
0x140075792  retn
```
