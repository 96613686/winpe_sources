# CNotification::SchdpEventWrite(ulong)

- ea: `0x180002b88`
- end: `0x180002dd7`
- name: `?SchdpEventWrite@CNotification@@AEAAJK@Z`
- size: `591`
- prototype: `__int64 __fastcall(CNotification *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180004590`
- `0x1800048bc`
- `0x180005d78`

## callees

- `0x180002b88`
- `0x180003a94`
- `0x18000b13c`
- `0x18000c836`
- `0x18000c860`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180002da3`
- `KERNEL32!HeapFree` at `0x180002da3`
- `KERNEL32!GetProcessHeap` at `0x180002c12`
- `KERNEL32!GetProcessHeap` at `0x180002d8f`
- `KERNEL32!GetProcessHeap` at `0x180002c12`
- `KERNEL32!GetProcessHeap` at `0x180002d8f`
- `KERNEL32!HeapAlloc` at `0x180002c26`
- `KERNEL32!HeapAlloc` at `0x180002c26`
- `ADVAPI32!EventWrite` at `0x180002d10`
- `ADVAPI32!EventWrite` at `0x180002d10`
- `OLEAUT32!__imp_SysFreeString` at `0x180002d7a`
- `OLEAUT32!__imp_SysFreeString` at `0x180002d7a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180002d50`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180002d50`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180002c94`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180002c94`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180002cad`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180002cad`

## string_xrefs

- `0x180002d38`: `CNotification::SchdpEventWrite`

## pseudocode

```c
__int64 __fastcall CNotification::SchdpEventWrite(CNotification *this, int a2)
{
  USHORT v2; // ax
  struct _EVENT_DATA_DESCRIPTOR *v3; // rdi
  ULONG v4; // r14d
  int v5; // eax
  signed int v6; // ebx
  int v7; // r9d
  int v8; // r8d
  ULONG cElements; // eax
  SIZE_T v10; // rbx
  HANDLE ProcessHeap; // rax
  struct _EVENT_DATA_DESCRIPTOR *v12; // rax
  int v13; // r15d
  SAFEARRAY *v14; // rcx
  signed int v15; // esi
  HRESULT Element; // eax
  UINT v17; // eax
  struct _EVENT_DATA_DESCRIPTOR *v18; // rdx
  UINT v19; // ecx
  BSTR v20; // rax
  signed int v21; // eax
  BSTR *v22; // rsi
  __int64 v23; // r14
  HANDLE v24; // rax
  LONG rgIndices; // [rsp+20h] [rbp-30h] BYREF
  SAFEARRAY *psa; // [rsp+28h] [rbp-28h] BYREF
  BSTR pv; // [rsp+30h] [rbp-20h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-18h] BYREF
  int v30; // [rsp+88h] [rbp+38h] BYREF

  v30 = a2;
  v2 = *(_WORD *)this;
  psa = 0;
  v3 = 0;
  pv = 0;
  EventDescriptor = (EVENT_DESCRIPTOR)SCHEDULED_DIAGNOSTICS_EVENT_WHC_NOTIFICATION;
  EventDescriptor.Id = v2;
  EventDescriptor.Version = *((_BYTE *)this + 2);
  v4 = 1;
  v5 = CNotification::SchdpSubstituteParameters(this, &psa);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = v5;
    v8 = 798;
LABEL_20:
    SdpDebugTrace(1u, L"CNotification::SchdpEventWrite", v8, v7);
    goto LABEL_21;
  }
  cElements = (unsigned int)psa;
  if ( psa )
    cElements = psa->rgsabound[0].cElements;
  v4 = cElements + 1;
  v10 = 16LL * (cElements + 1);
  ProcessHeap = GetProcessHeap();
  v12 = (struct _EVENT_DATA_DESCRIPTOR *)HeapAlloc(ProcessHeap, 0, v10);
  v3 = v12;
  if ( !v12 )
  {
    v6 = -2147024882;
    v8 = 805;
LABEL_19:
    v7 = v6;
    goto LABEL_20;
  }
  memset_0(v12, 0, v10);
  v13 = 0;
  v3->Size = 4;
  v3->Reserved = 0;
  v3->Ptr = (ULONGLONG)&v30;
  v14 = psa;
  if ( psa )
  {
    v15 = psa->rgsabound[0].cElements;
    if ( (unsigned int)v15 > 0x7FFFFFFF )
    {
      v6 = -2147024362;
      v8 = 816;
      goto LABEL_19;
    }
    rgIndices = 0;
    if ( v15 > 0 )
    {
      while ( 1 )
      {
        Element = SafeArrayGetElement(v14, &rgIndices, &pv);
        v6 = Element;
        if ( Element < 0 )
          break;
        ++v13;
        v17 = SysStringByteLen(pv);
        v18 = &v3[v13];
        v19 = v17 + 2;
        v20 = pv;
        v18->Reserved = 0;
        v18->Ptr = (ULONGLONG)v20;
        LODWORD(v20) = rgIndices + 1;
        v18->Size = v19;
        rgIndices = (int)v20;
        if ( (int)v20 >= v15 )
          goto LABEL_15;
        v14 = psa;
      }
      v7 = Element;
      v8 = 820;
      goto LABEL_20;
    }
  }
LABEL_15:
  v21 = EventWrite(SCHEDULED_DIAGNOSTICS_PROVIDER_Context, &EventDescriptor, v4, v3);
  v6 = v21;
  if ( v21 > 0 )
    v6 = (unsigned __int16)v21 | 0x80070000;
  if ( v6 < 0 )
  {
    v8 = 837;
    goto LABEL_19;
  }
LABEL_21:
  if ( psa )
  {
    SafeArrayDestroy(psa);
    psa = 0;
  }
  if ( v3 )
  {
    if ( v4 > 1 )
    {
      v22 = (BSTR *)&v3[1];
      v23 = v4 - 1;
      do
      {
        if ( *v22 )
          SysFreeString(*v22);
        v22 += 2;
        --v23;
      }
      while ( v23 );
    }
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v3);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002b88  mov     [rsp-28h+arg_10], rbx
0x180002b8d  mov     [rsp-28h+arg_18], rsi
0x180002b92  mov     [rsp-28h+arg_8], edx
0x180002b96  push    rbp
0x180002b97  push    rdi
0x180002b98  push    r13
0x180002b9a  push    r14
0x180002b9c  push    r15
0x180002b9e  mov     rbp, rsp
0x180002ba1  sub     rsp, 50h
0x180002ba5  mov     rax, cs:__security_cookie
0x180002bac  xor     rax, rsp
0x180002baf  mov     [rbp+var_8], rax
0x180002bb3  movzx   eax, word ptr [rcx]
0x180002bb6  lea     rdx, [rbp+psa]; struct tagSAFEARRAY **
0x180002bba  movups  xmm0, cs:SCHEDULED_DIAGNOSTICS_EVENT_WHC_NOTIFICATION
0x180002bc1  and     [rbp+psa], 0
0x180002bc6  xor     edi, edi
0x180002bc8  and     [rbp+pv], rdi
0x180002bcc  movdqu  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x180002bd1  mov     [rbp+EventDescriptor.Id], ax
0x180002bd5  mov     al, [rcx+2]
0x180002bd8  lea     r13d, [rdi+1]
0x180002bdc  mov     [rbp+EventDescriptor.Version], al
0x180002bdf  mov     r14d, r13d
0x180002be2  call    ?SchdpSubstituteParameters@CNotification@@AEAAJPEAPEAUtagSAFEARRAY@@@Z; CNotification::SchdpSubstituteParameters(tagSAFEARRAY * *)
0x180002be7  mov     ebx, eax
0x180002be9  test    eax, eax
0x180002beb  jns     short loc_180002BFB
0x180002bed  mov     r9d, eax
0x180002bf0  mov     r8d, 31Eh
0x180002bf6  jmp     loc_180002D38
0x180002bfb  mov     rax, [rbp+psa]
0x180002bff  test    rax, rax
0x180002c02  jz      short loc_180002C07
0x180002c04  mov     eax, [rax+18h]
0x180002c07  lea     r14d, [rax+1]
0x180002c0b  mov     ebx, r14d
0x180002c0e  shl     rbx, 4
0x180002c12  call    cs:__imp_GetProcessHeap
0x180002c19  nop     dword ptr [rax+rax+00h]
0x180002c1e  mov     r8, rbx; dwBytes
0x180002c21  xor     edx, edx; dwFlags
0x180002c23  mov     rcx, rax; hHeap
0x180002c26  call    cs:__imp_HeapAlloc
0x180002c2d  nop     dword ptr [rax+rax+00h]
0x180002c32  mov     rdi, rax
0x180002c35  test    rax, rax
0x180002c38  jnz     short loc_180002C4A
0x180002c3a  mov     ebx, 8007000Eh
0x180002c3f  mov     r8d, 325h
0x180002c45  jmp     loc_180002D35
0x180002c4a  mov     r8, rbx; Size
0x180002c4d  xor     edx, edx; Val
0x180002c4f  mov     rcx, rdi; void *
0x180002c52  call    memset_0
0x180002c57  xor     r15d, r15d
0x180002c5a  mov     dword ptr [rdi+8], 4
0x180002c61  and     [rdi+0Ch], r15d
0x180002c65  lea     rax, [rbp+arg_8]
0x180002c69  mov     [rdi], rax
0x180002c6c  mov     rcx, [rbp+psa]; psa
0x180002c70  test    rcx, rcx
0x180002c73  jz      loc_180002CFF
0x180002c79  mov     esi, [rcx+18h]
0x180002c7c  cmp     esi, 7FFFFFFFh
0x180002c82  ja      short loc_180002CF2
0x180002c84  and     [rbp+rgIndices], r15d
0x180002c88  test    esi, esi
0x180002c8a  jle     short loc_180002CFF
0x180002c8c  lea     r8, [rbp+pv]; pv
0x180002c90  lea     rdx, [rbp+rgIndices]; rgIndices
0x180002c94  call    cs:__imp_SafeArrayGetElement
0x180002c9b  nop     dword ptr [rax+rax+00h]
0x180002ca0  mov     ebx, eax
0x180002ca2  test    eax, eax
0x180002ca4  js      short loc_180002CE7
0x180002ca6  mov     rcx, [rbp+pv]; bstr
0x180002caa  add     r15d, r13d
0x180002cad  call    cs:__imp_SysStringByteLen
0x180002cb4  nop     dword ptr [rax+rax+00h]
0x180002cb9  mov     edx, r15d
0x180002cbc  shl     rdx, 4
0x180002cc0  add     rdx, rdi
0x180002cc3  lea     ecx, [rax+2]
0x180002cc6  mov     rax, [rbp+pv]
0x180002cca  and     dword ptr [rdx+0Ch], 0
0x180002cce  mov     [rdx], rax
0x180002cd1  mov     eax, [rbp+rgIndices]
0x180002cd4  add     eax, r13d
0x180002cd7  mov     [rdx+8], ecx
0x180002cda  mov     [rbp+rgIndices], eax
0x180002cdd  cmp     eax, esi
0x180002cdf  jge     short loc_180002CFF
0x180002ce1  mov     rcx, [rbp+psa]
0x180002ce5  jmp     short loc_180002C8C
0x180002ce7  mov     r9d, eax
0x180002cea  mov     r8d, 334h
0x180002cf0  jmp     short loc_180002D38
0x180002cf2  mov     ebx, 80070216h
0x180002cf7  mov     r8d, 330h
0x180002cfd  jmp     short loc_180002D35
0x180002cff  mov     rcx, cs:SCHEDULED_DIAGNOSTICS_PROVIDER_Context; RegHandle
0x180002d06  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x180002d0a  mov     r9, rdi; UserData
0x180002d0d  mov     r8d, r14d; UserDataCount
0x180002d10  call    cs:__imp_EventWrite
0x180002d17  nop     dword ptr [rax+rax+00h]
0x180002d1c  mov     ebx, eax
0x180002d1e  test    eax, eax
0x180002d20  jle     short loc_180002D2B
0x180002d22  movzx   ebx, ax
0x180002d25  or      ebx, 80070000h
0x180002d2b  test    ebx, ebx
0x180002d2d  jns     short loc_180002D47
0x180002d2f  mov     r8d, 345h; int
0x180002d35  mov     r9d, ebx; int
0x180002d38  lea     rdx, aCnotificationS_1; "CNotification::SchdpEventWrite"
0x180002d3f  mov     ecx, r13d; Level
0x180002d42  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002d47  mov     rcx, [rbp+psa]; psa
0x180002d4b  test    rcx, rcx
0x180002d4e  jz      short loc_180002D61
0x180002d50  call    cs:__imp_SafeArrayDestroy
0x180002d57  nop     dword ptr [rax+rax+00h]
0x180002d5c  and     [rbp+psa], 0
0x180002d61  test    rdi, rdi
0x180002d64  jz      short loc_180002DAF
0x180002d66  cmp     r14d, r13d
0x180002d69  jbe     short loc_180002D8F
0x180002d6b  lea     rsi, [rdi+10h]
0x180002d6f  dec     r14d
0x180002d72  mov     rcx, [rsi]; bstrString
0x180002d75  test    rcx, rcx
0x180002d78  jz      short loc_180002D86
0x180002d7a  call    cs:__imp_SysFreeString
0x180002d81  nop     dword ptr [rax+rax+00h]
0x180002d86  add     rsi, 10h
0x180002d8a  sub     r14, r13
0x180002d8d  jnz     short loc_180002D72
0x180002d8f  call    cs:__imp_GetProcessHeap
0x180002d96  nop     dword ptr [rax+rax+00h]
0x180002d9b  mov     r8, rdi; lpMem
0x180002d9e  xor     edx, edx; dwFlags
0x180002da0  mov     rcx, rax; hHeap
0x180002da3  call    cs:__imp_HeapFree
0x180002daa  nop     dword ptr [rax+rax+00h]
0x180002daf  mov     eax, ebx
0x180002db1  mov     rcx, [rbp+var_8]
0x180002db5  xor     rcx, rsp; StackCookie
0x180002db8  call    __security_check_cookie
0x180002dbd  lea     r11, [rsp+50h+var_s0]
0x180002dc2  mov     rbx, [r11+40h]
0x180002dc6  mov     rsi, [r11+48h]
0x180002dca  mov     rsp, r11
0x180002dcd  pop     r15
0x180002dcf  pop     r14
0x180002dd1  pop     r13
0x180002dd3  pop     rdi
0x180002dd4  pop     rbp
0x180002dd5  retn
```
