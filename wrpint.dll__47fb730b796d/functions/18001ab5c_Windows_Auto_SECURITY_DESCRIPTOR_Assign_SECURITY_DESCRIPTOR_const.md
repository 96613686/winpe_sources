# Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)

- ea: `0x18001ab5c`
- end: `0x18001ad49`
- name: `?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `493`
- prototype: `__int64 __fastcall(_QWORD *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001aed4`

## callees

- `0x1800054f0`
- `0x180007568`
- `0x18001ab5c`
- `0x18001b762`
- `0x18001b7b0`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x18001abf7`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18001abf7`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18001ac97`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18001ad0f`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18001ac97`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18001ad0f`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18001aba1`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18001aba1`
- `ntdll!RtlAllocateHeap` at `0x18001ac11`
- `ntdll!RtlAllocateHeap` at `0x18001acdc`
- `ntdll!RtlAllocateHeap` at `0x18001ac11`
- `ntdll!RtlAllocateHeap` at `0x18001acdc`

## string_xrefs

- `0x18001abbc`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18001ac2e`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18001abce`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x18001ac43`: `Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign`
- `0x18001abb5`: `RtlGetControlSecurityDescriptor(pTempSd, &Control, &Revision)`
- `0x18001ac27`: `m_pSD = RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, Size)`
- `0x18001acf5`: `m_pSD = ::RtlAllocateHeap((((PPEB)__readgsqword(((LONG)__builtin_offsetof(TEB, ProcessEnvironmentBlock))))->ProcessHeap), 0, cbSecurityDescriptor)`
- `0x18001ad27`: `RtlMakeSelfRelativeSD( pTempSd, m_pSD, &cbSecurityDescriptor)`

## pseudocode

```c
__int64 __fastcall Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_QWORD *a1, void *a2)
{
  __int64 v4; // rdx
  NTSTATUS ControlSecurityDescriptor; // ebx
  SIZE_T v7; // rbx
  PVOID v8; // rax
  PVOID v9; // rdx
  NTSTATUS SelfRelativeSD; // eax
  PVOID Heap; // rax
  WORD Control[2]; // [rsp+40h] [rbp-20h] BYREF
  ULONG BufferLength; // [rsp+44h] [rbp-1Ch] BYREF
  ULONG Revision; // [rsp+48h] [rbp-18h] BYREF

  if ( *a1 )
    INTERNAL_ERROR_ACTION(-1073741595);
  Revision = 0;
  Control[0] = 0;
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(a2, Control, &Revision);
  if ( ControlSecurityDescriptor < 0 )
    goto LABEL_3;
  if ( (Control[0] & 0x8000u) == 0 )
  {
    BufferLength = 0;
    SelfRelativeSD = RtlMakeSelfRelativeSD(a2, 0, &BufferLength);
    ControlSecurityDescriptor = SelfRelativeSD;
    if ( SelfRelativeSD == -2147483643 || SelfRelativeSD == -1073741789 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, BufferLength);
      *a1 = Heap;
      v9 = Heap;
      if ( !Heap )
        goto LABEL_6;
      a1[1] = BufferLength;
      ControlSecurityDescriptor = RtlMakeSelfRelativeSD(a2, Heap, &BufferLength);
      if ( ControlSecurityDescriptor >= 0 )
        return 0;
    }
    else if ( SelfRelativeSD >= 0 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
    }
LABEL_3:
    RtlReportErrorOrigination(
      "Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign",
      v4,
      (unsigned int)ControlSecurityDescriptor);
    return (unsigned int)ControlSecurityDescriptor;
  }
  v7 = RtlLengthSecurityDescriptor(a2);
  v8 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  *a1 = v8;
  if ( !v8 )
  {
LABEL_6:
    RtlReportErrorOrigination("Windows::Auto<struct _SECURITY_DESCRIPTOR>::Assign", v9, 3221225495LL);
    return 3221225495LL;
  }
  memcpy_0(v8, a2, v7);
  a1[1] = v7;
  return 0;
}

```

## disassembly

```asm
0x18001ab5c  mov     [rsp-18h+arg_10], rbx
0x18001ab61  push    rbp
0x18001ab62  push    rsi
0x18001ab63  push    rdi
0x18001ab64  mov     rbp, rsp
0x18001ab67  sub     rsp, 60h
0x18001ab6b  mov     rax, cs:__security_cookie
0x18001ab72  xor     rax, rsp
0x18001ab75  mov     [rbp+var_10], rax
0x18001ab79  cmp     qword ptr [rcx], 0
0x18001ab7d  mov     rdi, rdx
0x18001ab80  mov     rsi, rcx
0x18001ab83  jnz     loc_18001AD33
0x18001ab89  xor     eax, eax
0x18001ab8b  mov     [rbp+Revision], 0
0x18001ab92  lea     r8, [rbp+Revision]; Revision
0x18001ab96  mov     [rbp+Control], ax
0x18001ab9a  lea     rdx, [rbp+Control]; Control
0x18001ab9e  mov     rcx, rdi; SecurityDescriptor
0x18001aba1  call    cs:__imp_RtlGetControlSecurityDescriptor
0x18001aba7  mov     ebx, eax
0x18001aba9  test    eax, eax
0x18001abab  jns     short loc_18001ABE5
0x18001abad  mov     [rbp+var_30], 335h
0x18001abb5  lea     rax, aRtlgetcontrols; "RtlGetControlSecurityDescriptor(pTempSd"...
0x18001abbc  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18001abc3  mov     [rbp+var_28], rax
0x18001abc7  mov     [rbp+var_40], rcx
0x18001abcb  mov     r8d, ebx
0x18001abce  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x18001abd5  mov     [rbp+var_38], rcx
0x18001abd9  call    RtlReportErrorOrigination
0x18001abde  mov     eax, ebx
0x18001abe0  jmp     loc_18001AC6E
0x18001abe5  mov     eax, 8000h
0x18001abea  mov     rcx, rdi; AbsoluteSD
0x18001abed  test    [rbp+Control], ax
0x18001abf1  jz      loc_18001AC8A
0x18001abf7  call    cs:__imp_RtlLengthSecurityDescriptor
0x18001abfd  mov     rcx, gs:60h
0x18001ac06  xor     edx, edx; Flags
0x18001ac08  mov     r8d, eax; Size
0x18001ac0b  mov     ebx, eax
0x18001ac0d  mov     rcx, [rcx+30h]; HeapHandle
0x18001ac11  call    cs:__imp_RtlAllocateHeap
0x18001ac17  mov     [rsi], rax
0x18001ac1a  test    rax, rax
0x18001ac1d  jnz     short loc_18001AC5A
0x18001ac1f  mov     [rbp+var_30], 33Bh
0x18001ac27  lea     rax, aMPsdRtlallocat; "m_pSD = RtlAllocateHeap((((PPEB)__readg"...
0x18001ac2e  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18001ac35  mov     [rbp+var_28], rax
0x18001ac39  mov     [rbp+var_40], rcx
0x18001ac3d  mov     r8d, 0C0000017h
0x18001ac43  lea     rcx, aWindowsAutoStr; "Windows::Auto<struct _SECURITY_DESCRIPT"...
0x18001ac4a  mov     [rbp+var_38], rcx
0x18001ac4e  call    RtlReportErrorOrigination
0x18001ac53  mov     eax, 0C0000017h
0x18001ac58  jmp     short loc_18001AC6E
0x18001ac5a  mov     r8, rbx; Size
0x18001ac5d  mov     rdx, rdi; Src
0x18001ac60  mov     rcx, rax; void *
0x18001ac63  call    memcpy_0
0x18001ac68  mov     [rsi+8], rbx
0x18001ac6c  xor     eax, eax
0x18001ac6e  mov     rcx, [rbp+var_10]
0x18001ac72  xor     rcx, rsp; StackCookie
0x18001ac75  call    __security_check_cookie
0x18001ac7a  mov     rbx, [rsp+60h+arg_10]
0x18001ac82  add     rsp, 60h
0x18001ac86  pop     rdi
0x18001ac87  pop     rsi
0x18001ac88  pop     rbp
0x18001ac89  retn
0x18001ac8a  lea     r8, [rbp+BufferLength]; BufferLength
0x18001ac8e  mov     [rbp+BufferLength], 0
0x18001ac95  xor     edx, edx; SelfRelativeSD
0x18001ac97  call    cs:__imp_RtlMakeSelfRelativeSD
0x18001ac9d  mov     ebx, eax
0x18001ac9f  cmp     eax, 80000005h
0x18001aca4  jz      short loc_18001ACC9
0x18001aca6  cmp     eax, 0C0000023h
0x18001acab  jz      short loc_18001ACC9
0x18001acad  test    eax, eax
0x18001acaf  jns     loc_18001AD3E
0x18001acb5  mov     [rbp+var_30], 349h
0x18001acbd  lea     rax, aTmpstatusNtsta; "((TmpStatus == ((NTSTATUS)0x80000005L))"...
0x18001acc4  jmp     loc_18001ABBC
0x18001acc9  mov     rcx, gs:60h
0x18001acd2  xor     edx, edx; Flags
0x18001acd4  mov     r8d, [rbp+BufferLength]; Size
0x18001acd8  mov     rcx, [rcx+30h]; HeapHandle
0x18001acdc  call    cs:__imp_RtlAllocateHeap
0x18001ace2  mov     [rsi], rax
0x18001ace5  mov     rdx, rax; SelfRelativeSD
0x18001ace8  test    rax, rax
0x18001aceb  jnz     short loc_18001AD01
0x18001aced  mov     [rbp+var_30], 34Bh
0x18001acf5  lea     rax, aMPsdRtlallocat_0; "m_pSD = ::RtlAllocateHeap((((PPEB)__rea"...
0x18001acfc  jmp     loc_18001AC2E
0x18001ad01  mov     eax, [rbp+BufferLength]
0x18001ad04  lea     r8, [rbp+BufferLength]; BufferLength
0x18001ad08  mov     rcx, rdi; AbsoluteSD
0x18001ad0b  mov     [rsi+8], rax
0x18001ad0f  call    cs:__imp_RtlMakeSelfRelativeSD
0x18001ad15  mov     ebx, eax
0x18001ad17  test    eax, eax
0x18001ad19  jns     loc_18001AC6C
0x18001ad1f  mov     [rbp+var_30], 352h
0x18001ad27  lea     rax, aRtlmakeselfrel; "RtlMakeSelfRelativeSD( pTempSd, m_pSD, "...
0x18001ad2e  jmp     loc_18001ABBC
0x18001ad33  mov     ecx, 0C00000E5h; int
0x18001ad38  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x18001ad3e  mov     ecx, 0C00000E5h; int
0x18001ad43  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
