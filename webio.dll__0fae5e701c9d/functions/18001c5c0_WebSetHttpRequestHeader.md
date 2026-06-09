# WebSetHttpRequestHeader

- ea: `0x18001c5c0`
- end: `0x18001c9d9`
- name: `WebSetHttpRequestHeader`
- size: `1049`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180081454`
- `0x1800822dc`

## callees

- `0x18001b150`
- `0x18001c5c0`
- `0x18001c9e0`
- `0x18001cb10`
- `0x18001d620`
- `0x18001f200`
- `0x18006dc40`
- `0x1800722f0`
- `0x180072c70`
- `0x180083b8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c75d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c75d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c857`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c857`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001c6b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001c6b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001c6d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001c6d4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001c716`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001c739`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001c893`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001c716`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001c739`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001c893`

## string_xrefs

- `0x18001c904`: `WebHttpHeaderDelete`
- `0x18001c97f`: `WebHttpHeaderReplace`

## pseudocode

```c
__int64 __fastcall WebSetHttpRequestHeader(unsigned __int64 a1, unsigned int a2, const char **a3)
{
  unsigned int appended; // esi
  char *v6; // r8
  RTL_SRWLOCK *v7; // rbx
  RTL_SRWLOCK *v8; // rdi
  char *Ptr; // rbx
  unsigned int v10; // eax
  int v11; // ecx
  const char *v12; // rdx
  const char *v13; // rcx
  const char *v14; // r9
  GUID ActivityId; // [rsp+68h] [rbp-50h] BYREF
  int v18; // [rsp+78h] [rbp-40h]

  appended = 0;
  ActivityId = 0;
  v18 = 0;
  if ( !WaHandleTableInitialized )
    return 6;
  if ( (a1 & 0xF0000000) != 0x30000000 )
    return 6;
  v6 = (char *)WaHandleTable + 64 * (unsigned __int64)BYTE4(a1);
  if ( (unsigned int)(unsigned __int16)(HIDWORD(a1) >> 8) >= *((_DWORD *)v6 + 4) )
    return 6;
  v7 = (RTL_SRWLOCK *)(32 * HIBYTE(a1) + *(_QWORD *)(*((_QWORD *)v6 + 1) + 8LL * (unsigned __int16)(HIDWORD(a1) >> 8)));
  if ( v7[3].Ptr != (PVOID)a1 )
    return 6;
  v8 = v7 + 2;
  AcquireSRWLockShared(v7 + 2);
  if ( v7[3].Ptr == (PVOID)a1 )
  {
    Ptr = (char *)v7->Ptr;
    _InterlockedIncrement((volatile signed __int32 *)Ptr + 1);
  }
  else
  {
    Ptr = 0;
  }
  ReleaseSRWLockShared(v8);
  if ( !Ptr )
    return 6;
  ActivityId = 0;
  v18 = 0;
  if ( !EventActivityIdControl(1u, &ActivityId) )
  {
    if ( (_BYTE)v18 )
      goto LABEL_13;
    LOBYTE(v18) = EventActivityIdControl(2u, (LPGUID)(Ptr + 4572)) == 0;
  }
  if ( !(_BYTE)v18 )
    ActivityId = 0;
LABEL_13:
  EnterCriticalSection((LPCRITICAL_SECTION)(Ptr + 8));
  if ( Ptr[56] || (v10 = *((_DWORD *)Ptr + 12)) == 0 )
  {
    appended = *((_DWORD *)Ptr + 13);
  }
  else
  {
    if ( v10 > 6 || (v11 = 82, !_bittest(&v11, v10)) )
    {
      appended = 5023;
      goto LABEL_22;
    }
    if ( a3 )
    {
      if ( a2 || !a3[1] )
      {
        if ( (a2 > 1 || (appended = WaDeleteRequestHeader(Ptr + 344, a3)) == 0) && a2 - 1 <= 1 )
          appended = WaAppendRequestHeader(Ptr + 4928, Ptr + 344, a3);
        goto LABEL_22;
      }
      goto LABEL_49;
    }
    if ( a2 )
    {
LABEL_49:
      appended = 87;
      goto LABEL_22;
    }
    WaTerminateHttpParsedRequestHeaders(Ptr + 344);
    memset_0(Ptr + 344, 0, 0x2D8u);
    *((_QWORD *)Ptr + 132) = Ptr + 1048;
    *((_QWORD *)Ptr + 131) = Ptr + 1048;
  }
LABEL_22:
  v12 = "<StructNULL>";
  v13 = "<StructNULL>";
  if ( a3 )
  {
    v12 = "<NULL>";
    v13 = "<NULL>";
    if ( *a3 )
      v13 = *a3;
    if ( a3[1] )
      v12 = a3[1];
  }
  if ( WaEtwEnabled )
  {
    if ( a2 == 2 )
    {
      v14 = "WebHttpHeaderAppend";
    }
    else if ( a2 )
    {
      if ( a2 == 1 )
        v14 = "WebHttpHeaderReplace";
      else
        v14 = "?";
    }
    else
    {
      v14 = "WebHttpHeaderDelete";
    }
    WaEtwTraceString(
      "0x%p: WebSetHttpRequestHeader returning %d for %s on Header Name (%s) Value (%s)",
      Ptr,
      appended,
      v14,
      v13,
      v12);
  }
  if ( appended )
  {
    Ptr[56] = 1;
    if ( !*((_DWORD *)Ptr + 13) )
      *((_DWORD *)Ptr + 13) = appended;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(Ptr + 8));
  if ( appended )
    WaCancelHttpRequest(Ptr);
  if ( !_InterlockedDecrement((volatile signed __int32 *)Ptr + 1) )
    WapDestroyHttpRequest(Ptr);
  if ( (_BYTE)v18 )
    EventActivityIdControl(2u, &ActivityId);
  return appended;
}

```

## disassembly

```asm
0x18001c5c0  mov     [rsp+arg_8], rbx
0x18001c5c5  mov     [rsp+arg_18], rsi
0x18001c5ca  push    rdi
0x18001c5cb  push    r12
0x18001c5cd  push    r13
0x18001c5cf  push    r14
0x18001c5d1  push    r15
0x18001c5d3  sub     rsp, 90h
0x18001c5da  mov     rax, cs:__security_cookie
0x18001c5e1  xor     rax, rsp
0x18001c5e4  mov     [rsp+0B8h+var_38], rax
0x18001c5ec  mov     r12, r8
0x18001c5ef  mov     r15d, edx
0x18001c5f2  mov     rax, rcx
0x18001c5f5  shr     rax, 20h
0x18001c5f9  mov     dword ptr [rsp+0B8h+var_70], ecx
0x18001c5fd  mov     dword ptr [rsp+0B8h+var_70+4], eax
0x18001c601  mov     dword ptr [rsp+0B8h+var_80], ecx
0x18001c605  mov     dword ptr [rsp+0B8h+var_80+4], eax
0x18001c609  xor     r13d, r13d
0x18001c60c  mov     [rsp+0B8h+var_84], r13d
0x18001c611  mov     esi, r13d
0x18001c614  mov     [rsp+0B8h+var_88], r13d
0x18001c619  mov     [rsp+0B8h+var_78], r13
0x18001c61e  xorps   xmm0, xmm0
0x18001c621  xor     eax, eax
0x18001c623  movups  [rsp+0B8h+var_60], xmm0
0x18001c628  movups  xmmword ptr [rsp+0B8h+ActivityId.Data1], xmm0
0x18001c62d  mov     [rsp+0B8h+var_40], eax
0x18001c631  cmp     cs:WaHandleTableInitialized, al
0x18001c637  jz      loc_18001C99A
0x18001c63d  and     ecx, 0F0000000h
0x18001c643  cmp     ecx, 30000000h
0x18001c649  jnz     loc_18001C99A
0x18001c64f  mov     r14, [rsp+0B8h+var_80]
0x18001c654  mov     rax, r14
0x18001c657  shr     rax, 20h
0x18001c65b  mov     rdx, rax
0x18001c65e  movzx   r8d, al
0x18001c662  shl     r8, 6
0x18001c666  add     r8, cs:WaHandleTable
0x18001c66d  shr     edx, 8
0x18001c670  movzx   eax, dx
0x18001c673  cmp     eax, [r8+10h]
0x18001c677  jnb     loc_18001C99A
0x18001c67d  mov     rcx, [rsp+0B8h+var_70]
0x18001c682  mov     rax, rcx
0x18001c685  shr     rax, 28h
0x18001c689  movzx   edx, ax
0x18001c68c  mov     rax, [r8+8]
0x18001c690  shr     rcx, 20h
0x18001c694  shr     rcx, 18h
0x18001c698  shl     rcx, 5
0x18001c69c  mov     rbx, [rax+rdx*8]
0x18001c6a0  add     rbx, rcx
0x18001c6a3  cmp     [rbx+18h], r14
0x18001c6a7  jnz     loc_18001C99A
0x18001c6ad  lea     rdi, [rbx+10h]
0x18001c6b1  mov     rcx, rdi; SRWLock
0x18001c6b4  call    cs:__imp_AcquireSRWLockShared
0x18001c6bb  nop     dword ptr [rax+rax+00h]
0x18001c6c0  cmp     [rbx+18h], r14
0x18001c6c4  jnz     loc_18001C8BB
0x18001c6ca  mov     rbx, [rbx]
0x18001c6cd  lock inc dword ptr [rbx+4]
0x18001c6d1  mov     rcx, rdi; SRWLock
0x18001c6d4  call    cs:__imp_ReleaseSRWLockShared
0x18001c6db  nop     dword ptr [rax+rax+00h]
0x18001c6e0  test    rbx, rbx
0x18001c6e3  jz      loc_18001C99A
0x18001c6e9  xorps   xmm0, xmm0
0x18001c6ec  xor     eax, eax
0x18001c6ee  movups  [rsp+0B8h+var_60], xmm0
0x18001c6f3  movups  xmmword ptr [rsp+0B8h+ActivityId.Data1], xmm0
0x18001c6f8  mov     [rsp+0B8h+var_40], eax
0x18001c6fc  movups  xmm0, xmmword ptr [rbx+11DCh]
0x18001c703  movups  [rsp+0B8h+var_60], xmm0
0x18001c708  mov     byte ptr [rsp+0B8h+var_40], al
0x18001c70c  lea     rdx, [rsp+0B8h+ActivityId]; ActivityId
0x18001c711  mov     ecx, 1; ControlCode
0x18001c716  call    cs:__imp_EventActivityIdControl
0x18001c71d  nop     dword ptr [rax+rax+00h]
0x18001c722  test    eax, eax
0x18001c724  jnz     short loc_18001C74E
0x18001c726  cmp     byte ptr [rsp+0B8h+var_40], sil
0x18001c72b  jnz     short loc_18001C759
0x18001c72d  lea     rdx, [rbx+11DCh]; ActivityId
0x18001c734  mov     ecx, 2; ControlCode
0x18001c739  call    cs:__imp_EventActivityIdControl
0x18001c740  nop     dword ptr [rax+rax+00h]
0x18001c745  test    eax, eax
0x18001c747  jnz     short loc_18001C74E
0x18001c749  mov     byte ptr [rsp+0B8h+var_40], 1
0x18001c74e  cmp     byte ptr [rsp+0B8h+var_40], sil
0x18001c753  jz      loc_18001C8AE
0x18001c759  lea     rcx, [rbx+8]; lpCriticalSection
0x18001c75d  call    cs:__imp_EnterCriticalSection
0x18001c764  nop     dword ptr [rax+rax+00h]
0x18001c769  cmp     [rbx+38h], sil
0x18001c76d  jnz     loc_18001C932
0x18001c773  mov     eax, [rbx+30h]
0x18001c776  test    eax, eax
0x18001c778  jz      loc_18001C932
0x18001c77e  cmp     eax, 6
0x18001c781  ja      loc_18001C966
0x18001c787  mov     ecx, 52h ; 'R'
0x18001c78c  bt      ecx, eax
0x18001c78f  jnb     loc_18001C966
0x18001c795  test    r12, r12
0x18001c798  jz      loc_18001C8C3
0x18001c79e  test    r15d, r15d
0x18001c7a1  jz      loc_18001C954
0x18001c7a7  cmp     r15d, 1
0x18001c7ab  jbe     loc_18001C910
0x18001c7b1  lea     eax, [r15-1]
0x18001c7b5  cmp     eax, 1
0x18001c7b8  ja      short loc_18001C7D6
0x18001c7ba  lea     rdx, [rbx+158h]
0x18001c7c1  lea     rcx, [rbx+1340h]
0x18001c7c8  mov     r8, r12
0x18001c7cb  call    WaAppendRequestHeader
0x18001c7d0  mov     esi, eax
0x18001c7d2  mov     [rsp+0B8h+var_88], eax
0x18001c7d6  lea     rdx, aStructnull; "<StructNULL>"
0x18001c7dd  mov     rcx, rdx
0x18001c7e0  mov     [rsp+0B8h+var_78], rdx
0x18001c7e5  test    r12, r12
0x18001c7e8  jz      short loc_18001C815
0x18001c7ea  lea     rdx, aNull; "<NULL>"
0x18001c7f1  mov     rcx, rdx
0x18001c7f4  mov     [rsp+0B8h+var_78], rdx
0x18001c7f9  mov     rax, [r12]
0x18001c7fd  test    rax, rax
0x18001c800  cmovnz  rcx, rax
0x18001c804  mov     [rsp+0B8h+var_78], rcx
0x18001c809  mov     rax, [r12+8]
0x18001c80e  test    rax, rax
0x18001c811  cmovnz  rdx, rax
0x18001c815  cmp     cs:WaEtwEnabled, 0
0x18001c81c  jz      short loc_18001C84B
0x18001c81e  cmp     r15d, 2
0x18001c822  jnz     loc_18001C8FF
0x18001c828  lea     r9, aWebhttpheadera; "WebHttpHeaderAppend"
0x18001c82f  mov     [rsp+0B8h+var_90], rdx
0x18001c834  mov     [rsp+0B8h+var_98], rcx
0x18001c839  mov     r8d, esi
0x18001c83c  mov     rdx, rbx
0x18001c83f  lea     rcx, a0xPWebsethttpr; "0x%p: WebSetHttpRequestHeader returning"...
0x18001c846  call    WaEtwTraceString
0x18001c84b  test    esi, esi
0x18001c84d  jnz     loc_18001C93E
0x18001c853  lea     rcx, [rbx+8]; lpCriticalSection
0x18001c857  call    cs:__imp_LeaveCriticalSection
0x18001c85e  nop     dword ptr [rax+rax+00h]
0x18001c863  test    esi, esi
0x18001c865  jnz     loc_18001C98B
0x18001c86b  mov     eax, 0FFFFFFFFh
0x18001c870  lock xadd [rbx+4], eax
0x18001c875  sub     eax, 1
0x18001c878  mov     dword ptr [rsp+0B8h+var_80], eax
0x18001c87c  jz      short loc_18001C8A4
0x18001c87e  cmp     byte ptr [rsp+0B8h+var_40], 0
0x18001c883  jz      loc_18001C99F
0x18001c889  lea     rdx, [rsp+0B8h+ActivityId]; ActivityId
0x18001c88e  mov     ecx, 2; ControlCode
0x18001c893  call    cs:__imp_EventActivityIdControl
0x18001c89a  nop     dword ptr [rax+rax+00h]
0x18001c89f  jmp     loc_18001C99F
0x18001c8a4  mov     rcx, rbx; lpMem
0x18001c8a7  call    WapDestroyHttpRequest
0x18001c8ac  jmp     short loc_18001C87E
0x18001c8ae  xorps   xmm0, xmm0
0x18001c8b1  movups  xmmword ptr [rsp+0B8h+ActivityId.Data1], xmm0
0x18001c8b6  jmp     loc_18001C759
0x18001c8bb  mov     rbx, r13
0x18001c8be  jmp     loc_18001C6D1
0x18001c8c3  test    r15d, r15d
0x18001c8c6  jnz     loc_18001C95F
0x18001c8cc  lea     rcx, [rbx+158h]
0x18001c8d3  call    WaTerminateHttpParsedRequestHeaders
0x18001c8d8  xor     edx, edx; Val
0x18001c8da  mov     r8d, 2D8h; Size
0x18001c8e0  lea     rcx, [rbx+158h]; void *
0x18001c8e7  call    memset_0
0x18001c8ec  lea     rax, [rbx+418h]
0x18001c8f3  mov     [rax+8], rax
0x18001c8f7  mov     [rax], rax
0x18001c8fa  jmp     loc_18001C7D6
0x18001c8ff  test    r15d, r15d
0x18001c902  jnz     short loc_18001C96D
0x18001c904  lea     r9, aWebhttpheaderd; "WebHttpHeaderDelete"
0x18001c90b  jmp     loc_18001C82F
0x18001c910  lea     rcx, [rbx+158h]
0x18001c917  mov     rdx, r12
0x18001c91a  call    WaDeleteRequestHeader
0x18001c91f  mov     esi, eax
0x18001c921  mov     [rsp+0B8h+var_88], eax
0x18001c925  test    eax, eax
0x18001c927  jz      loc_18001C7B1
0x18001c92d  jmp     loc_18001C7D6
0x18001c932  mov     esi, [rbx+34h]
0x18001c935  mov     [rsp+0B8h+var_88], esi
0x18001c939  jmp     loc_18001C7D6
0x18001c93e  mov     byte ptr [rbx+38h], 1
0x18001c942  cmp     dword ptr [rbx+34h], 0
0x18001c946  jnz     loc_18001C853
0x18001c94c  mov     [rbx+34h], esi
0x18001c94f  jmp     loc_18001C853
0x18001c954  cmp     [r12+8], rsi
0x18001c959  jz      loc_18001C7A7
0x18001c95f  mov     esi, 57h ; 'W'
0x18001c964  jmp     short loc_18001C935
0x18001c966  mov     esi, 139Fh
0x18001c96b  jmp     short loc_18001C935
0x18001c96d  cmp     r15d, 1
0x18001c971  jz      short loc_18001C97F
0x18001c973  lea     r9, asc_18009E840; "?"
0x18001c97a  jmp     loc_18001C82F
0x18001c97f  lea     r9, aWebhttpheaderr; "WebHttpHeaderReplace"
0x18001c986  jmp     loc_18001C82F
0x18001c98b  mov     edx, esi
0x18001c98d  mov     rcx, rbx
0x18001c990  call    WaCancelHttpRequest
0x18001c995  jmp     loc_18001C86B
0x18001c99a  mov     esi, 6
0x18001c99f  mov     [rsp+0B8h+var_84], esi
0x18001c9a3  jmp     short loc_18001C9A9
0x18001c9a5  mov     esi, [rsp+0B8h+var_84]
0x18001c9a9  mov     eax, esi
0x18001c9ab  mov     rcx, [rsp+0B8h+var_38]
0x18001c9b3  xor     rcx, rsp; StackCookie
0x18001c9b6  call    __security_check_cookie
0x18001c9bb  lea     r11, [rsp+0B8h+var_28]
0x18001c9c3  mov     rbx, [r11+38h]
0x18001c9c7  mov     rsi, [r11+48h]
0x18001c9cb  mov     rsp, r11
0x18001c9ce  pop     r15
0x18001c9d0  pop     r14
0x18001c9d2  pop     r13
0x18001c9d4  pop     r12
0x18001c9d6  pop     rdi
0x18001c9d7  retn
0x180091760  push    rbp
0x180091762  sub     rsp, 30h
0x180091766  mov     rbp, rdx
0x180091769  call    WaRaiseFailFastExceptionFilter
0x18009176f  add     rsp, 30h
0x180091773  pop     rbp
0x180091774  retn
```
