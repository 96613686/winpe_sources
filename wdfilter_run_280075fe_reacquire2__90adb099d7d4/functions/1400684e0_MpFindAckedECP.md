# MpFindAckedECP

- ea: `0x1400684e0`
- end: `0x1400685b9`
- name: `MpFindAckedECP`
- size: `217`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, LPCGUID EcpType)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140084be8`

## callees

- `0x1400118d0`
- `0x1400684e0`

## import_xrefs

- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140068523`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140068523`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14006857c`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14006857c`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14006855a`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14006855a`

## pseudocode

```c
NTSTATUS __fastcall MpFindAckedECP(PFLT_CALLBACK_DATA CallbackData, LPCGUID EcpType, PVOID *a3, ULONG *a4)
{
  NTSTATUS result; // eax
  NTSTATUS v8; // ebx
  PVOID EcpContext; // [rsp+30h] [rbp-38h] BYREF
  PECP_LIST EcpList; // [rsp+38h] [rbp-30h] BYREF
  ULONG EcpContextSize; // [rsp+40h] [rbp-28h] BYREF

  EcpList = 0;
  EcpContext = 0;
  EcpContextSize = 0;
  result = FltGetEcpListFromCallbackData(*(PFLT_FILTER *)(MpData + 16), CallbackData, &EcpList);
  if ( result >= 0 )
  {
    if ( EcpList )
    {
      result = FltFindExtraCreateParameter(
                 *(PFLT_FILTER *)(MpData + 16),
                 EcpList,
                 EcpType,
                 &EcpContext,
                 &EcpContextSize);
      v8 = result;
      if ( result < 0 )
        return result;
      if ( FltIsEcpAcknowledged(*(PFLT_FILTER *)(MpData + 16), EcpContext) )
      {
        result = v8;
        *a3 = EcpContext;
        *a4 = EcpContextSize;
        return result;
      }
    }
    return -1073741823;
  }
  return result;
}

```

## disassembly

```asm
0x1400684e0  push    rbx
0x1400684e2  push    rsi
0x1400684e3  push    rdi
0x1400684e4  sub     rsp, 50h
0x1400684e8  mov     rax, cs:__security_cookie
0x1400684ef  xor     rax, rsp
0x1400684f2  mov     [rsp+68h+var_20], rax
0x1400684f7  xor     eax, eax
0x1400684f9  mov     rbx, rdx
0x1400684fc  mov     rdx, rcx; CallbackData
0x1400684ff  mov     [rsp+68h+EcpList], rax
0x140068504  mov     rcx, cs:MpData
0x14006850b  mov     rdi, r8
0x14006850e  mov     [rsp+68h+EcpContext], rax
0x140068513  lea     r8, [rsp+68h+EcpList]; EcpList
0x140068518  mov     [rsp+68h+var_28], eax
0x14006851c  mov     rsi, r9
0x14006851f  mov     rcx, [rcx+10h]; Filter
0x140068523  call    cs:__imp_FltGetEcpListFromCallbackData
0x14006852a  nop     dword ptr [rax+rax+00h]
0x14006852f  test    eax, eax
0x140068531  js      short loc_140068591
0x140068533  mov     rdx, [rsp+68h+EcpList]; EcpList
0x140068538  test    rdx, rdx
0x14006853b  jz      short loc_14006858C
0x14006853d  mov     rcx, cs:MpData
0x140068544  lea     rax, [rsp+68h+var_28]
0x140068549  lea     r9, [rsp+68h+EcpContext]; EcpContext
0x14006854e  mov     [rsp+68h+EcpContextSize], rax; EcpContextSize
0x140068553  mov     r8, rbx; EcpType
0x140068556  mov     rcx, [rcx+10h]; Filter
0x14006855a  call    cs:__imp_FltFindExtraCreateParameter
0x140068561  nop     dword ptr [rax+rax+00h]
0x140068566  mov     ebx, eax
0x140068568  test    eax, eax
0x14006856a  js      short loc_140068591
0x14006856c  mov     rcx, cs:MpData
0x140068573  mov     rdx, [rsp+68h+EcpContext]; EcpContext
0x140068578  mov     rcx, [rcx+10h]; Filter
0x14006857c  call    cs:__imp_FltIsEcpAcknowledged
0x140068583  nop     dword ptr [rax+rax+00h]
0x140068588  test    al, al
0x14006858a  jnz     short loc_1400685A7
0x14006858c  mov     eax, 0C0000001h
0x140068591  mov     rcx, [rsp+68h+var_20]
0x140068596  xor     rcx, rsp; StackCookie
0x140068599  call    __security_check_cookie
0x14006859e  add     rsp, 50h
0x1400685a2  pop     rdi
0x1400685a3  pop     rsi
0x1400685a4  pop     rbx
0x1400685a5  retn
0x1400685a7  mov     rcx, [rsp+68h+EcpContext]
0x1400685ac  mov     eax, ebx
0x1400685ae  mov     [rdi], rcx
0x1400685b1  mov     ecx, [rsp+68h+var_28]
0x1400685b5  mov     [rsi], ecx
0x1400685b7  jmp     short loc_140068591
```
