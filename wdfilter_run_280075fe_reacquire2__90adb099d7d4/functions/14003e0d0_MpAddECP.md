# MpAddECP

- ea: `0x14003e0d0`
- end: `0x14003e37f`
- name: `MpAddECP`
- size: `687`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, LPCGUID EcpType, size_t Size)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14003c990`

## callees

- `0x1400018a4`
- `0x140011890`
- `0x1400118d0`
- `0x140011bc0`
- `0x14003e0d0`

## import_xrefs

- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14003e187`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14003e187`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14003e245`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14003e245`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003e118`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14003e118`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14003e2a7`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14003e2a7`
- `FLTMGR!FltSetEcpListIntoCallbackData` at `0x14003e1b3`
- `FLTMGR!FltSetEcpListIntoCallbackData` at `0x14003e1b3`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003e14e`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14003e14e`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14003e1f8`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14003e1f8`

## pseudocode

```c
__int64 __fastcall MpAddECP(
        PFLT_CALLBACK_DATA CallbackData,
        LPCGUID EcpType,
        size_t Size,
        void (__fastcall *a4)(PVOID))
{
  size_t v5; // rbp
  NTSTATUS EcpListFromCallbackData; // ebx
  struct _FLT_FILTER *v9; // rcx
  __int64 v11; // rdx
  PECP_LIST EcpList; // [rsp+40h] [rbp-58h] BYREF
  PVOID EcpContext; // [rsp+48h] [rbp-50h] BYREF

  v5 = (unsigned int)Size;
  EcpList = 0;
  EcpContext = 0;
  EcpListFromCallbackData = FltGetEcpListFromCallbackData(*(PFLT_FILTER *)(MpData + 16), CallbackData, &EcpList);
  if ( EcpListFromCallbackData < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return (unsigned int)EcpListFromCallbackData;
    v11 = 17;
    goto LABEL_18;
  }
  v9 = *(struct _FLT_FILTER **)(MpData + 16);
  if ( !EcpList )
  {
    EcpListFromCallbackData = FltAllocateExtraCreateParameterList(v9, 0, &EcpList);
    if ( EcpListFromCallbackData < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        return (unsigned int)EcpListFromCallbackData;
      v11 = 18;
    }
    else
    {
      _mm_lfence();
      EcpListFromCallbackData = FltSetEcpListIntoCallbackData(*(PFLT_FILTER *)(MpData + 16), CallbackData, EcpList);
      if ( EcpListFromCallbackData >= 0 )
        goto LABEL_7;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        return (unsigned int)EcpListFromCallbackData;
      v11 = 19;
    }
LABEL_18:
    _mm_lfence();
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v11,
      WPP_da25ed7ac0df3f6c27bc2dc1e0325faa_Traceguids,
      (unsigned int)EcpListFromCallbackData);
    return (unsigned int)EcpListFromCallbackData;
  }
  EcpListFromCallbackData = FltFindExtraCreateParameter(v9, EcpList, EcpType, 0, 0);
  if ( EcpListFromCallbackData != -1073741275 )
    return (unsigned int)EcpListFromCallbackData;
LABEL_7:
  EcpListFromCallbackData = FltAllocateExtraCreateParameterFromLookasideList(
                              *(PFLT_FILTER *)(MpData + 16),
                              EcpType,
                              v5,
                              0,
                              0,
                              (PVOID)(MpData + 1984),
                              &EcpContext);
  if ( EcpListFromCallbackData < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return (unsigned int)EcpListFromCallbackData;
    v11 = 20;
    goto LABEL_18;
  }
  memset(EcpContext, 0, v5);
  if ( a4 )
    a4(EcpContext);
  EcpListFromCallbackData = FltInsertExtraCreateParameter(*(PFLT_FILTER *)(MpData + 16), EcpList, EcpContext);
  if ( EcpListFromCallbackData < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        WPP_da25ed7ac0df3f6c27bc2dc1e0325faa_Traceguids,
        (unsigned int)EcpListFromCallbackData);
    }
    FltFreeExtraCreateParameter(*(PFLT_FILTER *)(MpData + 16), EcpContext);
  }
  return (unsigned int)EcpListFromCallbackData;
}

```

## disassembly

```asm
0x14003e0d0  push    rbx
0x14003e0d2  push    rbp
0x14003e0d3  push    rsi
0x14003e0d4  push    rdi
0x14003e0d5  push    r14
0x14003e0d7  push    r15
0x14003e0d9  sub     rsp, 68h
0x14003e0dd  mov     rax, cs:__security_cookie
0x14003e0e4  xor     rax, rsp
0x14003e0e7  mov     [rsp+98h+var_48], rax
0x14003e0ec  mov     rsi, rcx
0x14003e0ef  mov     ebp, r8d
0x14003e0f2  mov     r14, rdx
0x14003e0f5  lea     r8, [rsp+98h+EcpList]; EcpList
0x14003e0fa  mov     rdx, rcx; CallbackData
0x14003e0fd  xor     r15d, r15d
0x14003e100  mov     rcx, cs:MpData
0x14003e107  mov     rdi, r9
0x14003e10a  mov     [rsp+98h+EcpList], r15
0x14003e10f  mov     [rsp+98h+var_50], r15
0x14003e114  mov     rcx, [rcx+10h]; Filter
0x14003e118  call    cs:__imp_FltGetEcpListFromCallbackData
0x14003e11f  nop     dword ptr [rax+rax+00h]
0x14003e124  mov     ebx, eax
0x14003e126  test    eax, eax
0x14003e128  js      loc_14003E301
0x14003e12e  mov     rcx, cs:MpData
0x14003e135  mov     rdx, [rsp+98h+EcpList]; EcpList
0x14003e13a  mov     rcx, [rcx+10h]; Filter
0x14003e13e  test    rdx, rdx
0x14003e141  jz      short loc_14003E180
0x14003e143  xor     r9d, r9d; EcpContext
0x14003e146  mov     [rsp+98h+EcpContextSize], r15; EcpContextSize
0x14003e14b  mov     r8, r14; EcpType
0x14003e14e  call    cs:__imp_FltFindExtraCreateParameter
0x14003e155  nop     dword ptr [rax+rax+00h]
0x14003e15a  mov     ebx, eax
0x14003e15c  cmp     eax, 0C0000225h
0x14003e161  jz      short loc_14003E1C9
0x14003e163  mov     eax, ebx
0x14003e165  mov     rcx, [rsp+98h+var_48]
0x14003e16a  xor     rcx, rsp; StackCookie
0x14003e16d  call    __security_check_cookie
0x14003e172  add     rsp, 68h
0x14003e176  pop     r15
0x14003e178  pop     r14
0x14003e17a  pop     rdi
0x14003e17b  pop     rsi
0x14003e17c  pop     rbp
0x14003e17d  pop     rbx
0x14003e17e  retn
0x14003e180  lea     r8, [rsp+98h+EcpList]; EcpList
0x14003e185  xor     edx, edx; Flags
0x14003e187  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14003e18e  nop     dword ptr [rax+rax+00h]
0x14003e193  mov     ebx, eax
0x14003e195  test    eax, eax
0x14003e197  js      loc_14003E32A
0x14003e19d  lfence
0x14003e1a0  mov     rcx, cs:MpData
0x14003e1a7  mov     rdx, rsi; CallbackData
0x14003e1aa  mov     r8, [rsp+98h+EcpList]; EcpList
0x14003e1af  mov     rcx, [rcx+10h]; Filter
0x14003e1b3  call    cs:__imp_FltSetEcpListIntoCallbackData
0x14003e1ba  nop     dword ptr [rax+rax+00h]
0x14003e1bf  mov     ebx, eax
0x14003e1c1  test    eax, eax
0x14003e1c3  js      loc_14003E353
0x14003e1c9  mov     rcx, cs:MpData
0x14003e1d0  lea     rdx, [rsp+98h+var_50]
0x14003e1d5  mov     [rsp+98h+EcpContext], rdx; EcpContext
0x14003e1da  xor     r9d, r9d; Flags
0x14003e1dd  mov     r8d, ebp; SizeOfContext
0x14003e1e0  mov     rdx, r14; EcpType
0x14003e1e3  lea     rax, [rcx+7C0h]
0x14003e1ea  mov     rcx, [rcx+10h]; Filter
0x14003e1ee  mov     [rsp+98h+LookasideList], rax; LookasideList
0x14003e1f3  mov     [rsp+98h+EcpContextSize], r15; CleanupCallback
0x14003e1f8  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x14003e1ff  nop     dword ptr [rax+rax+00h]
0x14003e204  mov     ebx, eax
0x14003e206  test    eax, eax
0x14003e208  js      loc_14003E2B8
0x14003e20e  mov     rcx, [rsp+98h+var_50]; void *
0x14003e213  mov     r8, rbp; Size
0x14003e216  xor     edx, edx; Val
0x14003e218  call    memset
0x14003e21d  test    rdi, rdi
0x14003e220  jz      short loc_14003E230
0x14003e222  mov     rcx, [rsp+98h+var_50]
0x14003e227  mov     rax, rdi
0x14003e22a  call    cs:__guard_dispatch_icall_fptr
0x14003e230  mov     rcx, cs:MpData
0x14003e237  mov     r8, [rsp+98h+var_50]; EcpContext
0x14003e23c  mov     rdx, [rsp+98h+EcpList]; EcpList
0x14003e241  mov     rcx, [rcx+10h]; Filter
0x14003e245  call    cs:__imp_FltInsertExtraCreateParameter
0x14003e24c  nop     dword ptr [rax+rax+00h]
0x14003e251  mov     ebx, eax
0x14003e253  test    eax, eax
0x14003e255  jns     loc_14003E163
0x14003e25b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e262  lea     rax, WPP_GLOBAL_Control
0x14003e269  cmp     rcx, rax
0x14003e26c  jz      short loc_14003E297
0x14003e26e  mov     eax, [rcx+2Ch]
0x14003e271  test    al, 1
0x14003e273  jz      short loc_14003E297
0x14003e275  lfence
0x14003e278  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e27f  lea     r8, WPP_da25ed7ac0df3f6c27bc2dc1e0325faa_Traceguids
0x14003e286  mov     edx, 15h
0x14003e28b  mov     r9d, ebx
0x14003e28e  mov     rcx, [rcx+18h]
0x14003e292  call    WPP_SF_d
0x14003e297  mov     rcx, cs:MpData
0x14003e29e  mov     rdx, [rsp+98h+var_50]; EcpContext
0x14003e2a3  mov     rcx, [rcx+10h]; Filter
0x14003e2a7  call    cs:__imp_FltFreeExtraCreateParameter
0x14003e2ae  nop     dword ptr [rax+rax+00h]
0x14003e2b3  jmp     loc_14003E163
0x14003e2b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e2bf  lea     rax, WPP_GLOBAL_Control
0x14003e2c6  cmp     rcx, rax
0x14003e2c9  jz      loc_14003E163
0x14003e2cf  mov     eax, [rcx+2Ch]
0x14003e2d2  test    al, 1
0x14003e2d4  jz      loc_14003E163
0x14003e2da  mov     edx, 14h
0x14003e2df  lfence
0x14003e2e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e2e9  lea     r8, WPP_da25ed7ac0df3f6c27bc2dc1e0325faa_Traceguids
0x14003e2f0  mov     r9d, ebx
0x14003e2f3  mov     rcx, [rcx+18h]
0x14003e2f7  call    WPP_SF_d
0x14003e2fc  jmp     loc_14003E163
0x14003e301  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e308  lea     rax, WPP_GLOBAL_Control
0x14003e30f  cmp     rcx, rax
0x14003e312  jz      loc_14003E163
0x14003e318  mov     eax, [rcx+2Ch]
0x14003e31b  test    al, 1
0x14003e31d  jz      loc_14003E163
0x14003e323  mov     edx, 11h
0x14003e328  jmp     short loc_14003E2DF
0x14003e32a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e331  lea     rax, WPP_GLOBAL_Control
0x14003e338  cmp     rcx, rax
0x14003e33b  jz      loc_14003E163
0x14003e341  mov     eax, [rcx+2Ch]
0x14003e344  test    al, 1
0x14003e346  jz      loc_14003E163
0x14003e34c  mov     edx, 12h
0x14003e351  jmp     short loc_14003E2DF
0x14003e353  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e35a  lea     rax, WPP_GLOBAL_Control
0x14003e361  cmp     rcx, rax
0x14003e364  jz      loc_14003E163
0x14003e36a  mov     eax, [rcx+2Ch]
0x14003e36d  test    al, 1
0x14003e36f  jz      loc_14003E163
0x14003e375  mov     edx, 13h
0x14003e37a  jmp     loc_14003E2DF
```
