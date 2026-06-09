# COSInstaller::Cancel(int)

- ea: `0x180028710`
- end: `0x1800288f0`
- name: `?Cancel@COSInstaller@@UEAAJH@Z`
- size: `480`
- prototype: `__int64 __fastcall(COSInstaller *__hidden this, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x180003950`
- `0x18000956c`
- `0x180028710`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002876f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800287e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002876f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800287e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028758`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028758`

## string_xrefs

- `0x1800288da`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall COSInstaller::Cancel(COSInstaller *this, int a2)
{
  __int64 v4; // rdi
  char *v5; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // rbp
  __int64 v7; // rcx
  unsigned int v8; // ebx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = 0;
  v12 = 0;
  if ( *((_BYTE *)this + 56) )
    goto LABEL_7;
  *((_BYTE *)this + 56) = 1;
  v5 = (char *)this + 64;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  if ( this != (COSInstaller *)-64LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v7 = *((_QWORD *)this + 14);
  if ( !v7 )
  {
    if ( v5 )
      LeaveCriticalSection(v6);
    goto LABEL_7;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  v4 = *((_QWORD *)this + 14);
  if ( v5 )
    LeaveCriticalSection(v6);
  if ( !a2 )
    goto LABEL_22;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v4)(v4, &GUID_09110432_1aee_49f8_9c1c_0f7d203777bf, &v12) < 0 )
  {
    WUTrace(0, 0, 4096, 4);
LABEL_22:
    WUTrace(0, 0, 4096, 4);
    v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 64LL))(v4, 2149851144LL);
    v8 = v10;
    if ( v10 < 0 )
    {
      v11 = 679;
      goto LABEL_24;
    }
LABEL_7:
    v8 = 0;
    goto LABEL_8;
  }
  WUTrace(0, 0, 4096, 4);
  v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 96LL))(v12, 2149851144LL);
  v8 = v10;
  if ( v10 >= 0 )
    goto LABEL_7;
  v11 = 668;
LABEL_24:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
    (const char *)(unsigned int)v10,
    0);
LABEL_8:
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return v8;
}

```

## disassembly

```asm
0x180028710  mov     [rsp+arg_8], rbx
0x180028715  mov     [rsp+arg_10], rbp
0x18002871a  push    rsi
0x18002871b  push    rdi
0x18002871c  push    r14
0x18002871e  sub     rsp, 40h
0x180028722  mov     rax, cs:__security_cookie
0x180028729  xor     rax, rsp
0x18002872c  mov     [rsp+58h+var_20], rax
0x180028731  mov     r14d, edx
0x180028734  mov     rsi, rcx
0x180028737  xor     edi, edi
0x180028739  mov     [rsp+58h+var_28], rdi
0x18002873e  cmp     [rcx+38h], dil
0x180028742  jnz     short loc_180028775
0x180028744  mov     byte ptr [rcx+38h], 1
0x180028748  lea     rbx, [rcx+40h]
0x18002874c  lea     rbp, [rbx+8]
0x180028750  test    rbx, rbx
0x180028753  jz      short loc_18002875E
0x180028755  mov     rcx, rbp; lpCriticalSection
0x180028758  call    cs:__imp_EnterCriticalSection
0x18002875e  mov     rcx, [rsi+70h]
0x180028762  test    rcx, rcx
0x180028765  jnz     short loc_1800287CD
0x180028767  test    rbx, rbx
0x18002876a  jz      short loc_180028775
0x18002876c  mov     rcx, rbp; lpCriticalSection
0x18002876f  call    cs:__imp_LeaveCriticalSection
0x180028775  xor     ebx, ebx
0x180028777  mov     rcx, [rsp+58h+var_28]
0x18002877c  test    rcx, rcx
0x18002877f  jz      short loc_180028796
0x180028781  mov     rax, [rcx]
0x180028784  mov     rax, [rax+10h]
0x180028788  call    _guard_dispatch_icall
0x18002878d  mov     [rsp+58h+var_28], 0
0x180028796  test    rdi, rdi
0x180028799  jz      short loc_1800287AB
0x18002879b  mov     rcx, [rdi]
0x18002879e  mov     rax, [rcx+10h]
0x1800287a2  mov     rcx, rdi
0x1800287a5  call    _guard_dispatch_icall
0x1800287aa  nop
0x1800287ab  mov     eax, ebx
0x1800287ad  mov     rcx, [rsp+58h+var_20]
0x1800287b2  xor     rcx, rsp; StackCookie
0x1800287b5  call    __security_check_cookie
0x1800287ba  mov     rbx, [rsp+58h+arg_8]
0x1800287bf  mov     rbp, [rsp+58h+arg_10]
0x1800287c4  add     rsp, 40h
0x1800287c8  pop     r14
0x1800287ca  pop     rdi
0x1800287cb  pop     rsi
0x1800287cc  retn
0x1800287cd  mov     rax, [rcx]
0x1800287d0  mov     rax, [rax+8]
0x1800287d4  call    _guard_dispatch_icall
0x1800287d9  mov     rdi, [rsi+70h]
0x1800287dd  test    rbx, rbx
0x1800287e0  jz      short loc_1800287EB
0x1800287e2  mov     rcx, rbp; lpCriticalSection
0x1800287e5  call    cs:__imp_LeaveCriticalSection
0x1800287eb  mov     ebx, 4
0x1800287f0  mov     esi, 1000h
0x1800287f5  test    r14d, r14d
0x1800287f8  jz      loc_180028890
0x1800287fe  mov     rcx, [rsp+58h+var_28]
0x180028803  test    rcx, rcx
0x180028806  jz      short loc_180028814
0x180028808  mov     rax, [rcx]
0x18002880b  mov     rax, [rax+10h]
0x18002880f  call    _guard_dispatch_icall
0x180028814  mov     rax, [rdi]
0x180028817  lea     r8, [rsp+58h+var_28]
0x18002881c  lea     rdx, _GUID_09110432_1aee_49f8_9c1c_0f7d203777bf
0x180028823  mov     rcx, rdi
0x180028826  mov     rax, [rax]
0x180028829  call    _guard_dispatch_icall
0x18002882e  mov     r9d, ebx
0x180028831  mov     r8d, esi
0x180028834  xor     edx, edx
0x180028836  test    eax, eax
0x180028838  js      short loc_180028879
0x18002883a  lea     rax, aCallingSuspend; "Calling Suspend"
0x180028841  mov     [rsp+58h+var_30], rax
0x180028846  mov     qword ptr [rsp+58h+var_38], rdx
0x18002884b  xor     ecx, ecx
0x18002884d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028852  mov     rcx, [rsp+58h+var_28]
0x180028857  mov     rax, [rcx]
0x18002885a  mov     edx, 80242008h
0x18002885f  mov     rax, [rax+60h]
0x180028863  call    _guard_dispatch_icall
0x180028868  mov     ebx, eax
0x18002886a  test    eax, eax
0x18002886c  jns     loc_180028775
0x180028872  mov     edx, 29Ch
0x180028877  jmp     short loc_1800288D7
0x180028879  lea     rcx, aSuspendApiNotA; "Suspend API not available, calling Canc"...
0x180028880  mov     [rsp+58h+var_30], rcx
0x180028885  mov     [rsp+58h+var_38], eax
0x180028889  xor     ecx, ecx
0x18002888b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180028890  lea     rax, aCallingCancel; "Calling Cancel"
0x180028897  mov     [rsp+58h+var_30], rax
0x18002889c  mov     qword ptr [rsp+58h+var_38], 0; int
0x1800288a5  mov     r9d, ebx
0x1800288a8  mov     r8d, esi
0x1800288ab  xor     edx, edx
0x1800288ad  xor     ecx, ecx
0x1800288af  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800288b4  mov     rax, [rdi]
0x1800288b7  mov     edx, 80242008h
0x1800288bc  mov     rcx, rdi
0x1800288bf  mov     rax, [rax+40h]
0x1800288c3  call    _guard_dispatch_icall
0x1800288c8  mov     ebx, eax
0x1800288ca  test    eax, eax
0x1800288cc  jns     loc_180028775
0x1800288d2  mov     edx, 2A7h; void *
0x1800288d7  mov     r9d, eax; char *
0x1800288da  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800288e1  mov     rcx, [rsp+58h]; this
0x1800288e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800288eb  jmp     loc_180028777
```
