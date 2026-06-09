# P2P_REQUEST::OnReceiveHttpResponseEntity(uchar *,ulong)

- ea: `0x18008a984`
- end: `0x18008aace`
- name: `?OnReceiveHttpResponseEntity@P2P_REQUEST@@QEAAKPEAEK@Z`
- size: `330`
- prototype: `unsigned int __fastcall(P2P_REQUEST *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18008a338`

## callees

- `0x180072c70`
- `0x18008a984`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a9c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a9c9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008a9b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008a9b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008aa3e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008aaa2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008aa3e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008aaa2`

## pseudocode

```c
DWORD __fastcall P2P_REQUEST::OnReceiveHttpResponseEntity(P2P_REQUEST *this, unsigned __int8 *a2, unsigned int a3)
{
  HANDLE EventW; // rax
  DWORD result; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx

  if ( *((_DWORD *)this + 34) )
    return 0;
  if ( !*((_QWORD *)this + 13) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 13) = EventW;
    if ( !EventW )
      return GetLastError();
  }
  if ( a3 )
  {
    if ( *((_QWORD *)this + 2) )
    {
      memset_0((char *)this + 24, 0, 0x50u);
      v8 = *((_QWORD *)this + 2);
      v9 = *(_QWORD *)this;
      *((_QWORD *)this + 10) = *((_QWORD *)this + 13);
      result = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, unsigned __int8 *, char *))qword_1800AE638)(
                 v9,
                 *(_QWORD *)(v8 + 8),
                 a3,
                 a2,
                 (char *)this + 56);
      if ( result == 997 )
      {
        WaitForSingleObject(*((HANDLE *)this + 10), 0xFFFFFFFF);
        result = *((_DWORD *)this + 14);
      }
    }
    else
    {
      result = 6;
    }
  }
  else
  {
    if ( *((_DWORD *)this + 28) )
      return 0;
    if ( *((_QWORD *)this + 2) )
    {
      memset_0((char *)this + 24, 0, 0x50u);
      v10 = *((_QWORD *)this + 2);
      v11 = *(_QWORD *)this;
      *((_QWORD *)this + 10) = *((_QWORD *)this + 13);
      result = ((__int64 (__fastcall *)(__int64, _QWORD, char *))qword_1800AE640)(
                 v11,
                 *(_QWORD *)(v10 + 8),
                 (char *)this + 56);
      if ( result == 997 )
      {
        WaitForSingleObject(*((HANDLE *)this + 10), 0xFFFFFFFF);
        result = *((_DWORD *)this + 14);
      }
    }
    else
    {
      result = 6;
    }
    *((_DWORD *)this + 28) = 1;
  }
  if ( !result )
    return result;
  *((_DWORD *)this + 34) = result;
  return 0;
}

```

## disassembly

```asm
0x18008a984  push    rbx
0x18008a986  push    rbp
0x18008a987  push    rsi
0x18008a988  push    rdi
0x18008a989  sub     rsp, 38h
0x18008a98d  cmp     dword ptr [rcx+88h], 0
0x18008a994  mov     edi, r8d
0x18008a997  mov     rbp, rdx
0x18008a99a  mov     rbx, rcx
0x18008a99d  jnz     loc_18008AAC2
0x18008a9a3  cmp     qword ptr [rcx+68h], 0
0x18008a9a8  jnz     short loc_18008A9DA
0x18008a9aa  xor     r9d, r9d; lpName
0x18008a9ad  xor     r8d, r8d; bInitialState
0x18008a9b0  xor     edx, edx; bManualReset
0x18008a9b2  xor     ecx, ecx; lpEventAttributes
0x18008a9b4  call    cs:__imp_CreateEventW
0x18008a9bb  nop     dword ptr [rax+rax+00h]
0x18008a9c0  mov     [rbx+68h], rax
0x18008a9c4  test    rax, rax
0x18008a9c7  jnz     short loc_18008A9DA
0x18008a9c9  call    cs:__imp_GetLastError
0x18008a9d0  nop     dword ptr [rax+rax+00h]
0x18008a9d5  jmp     loc_18008AAC4
0x18008a9da  test    edi, edi
0x18008a9dc  jz      short loc_18008AA4E
0x18008a9de  cmp     qword ptr [rbx+10h], 0
0x18008a9e3  jnz     short loc_18008A9EF
0x18008a9e5  mov     eax, 6
0x18008a9ea  jmp     loc_18008AAB8
0x18008a9ef  xor     edx, edx; Val
0x18008a9f1  lea     rcx, [rbx+18h]; void *
0x18008a9f5  lea     r8d, [rdx+50h]; Size
0x18008a9f9  call    memset_0
0x18008a9fe  mov     rax, [rbx+68h]
0x18008aa02  lea     rsi, [rbx+38h]
0x18008aa06  mov     rdx, [rbx+10h]
0x18008aa0a  mov     r9, rbp
0x18008aa0d  mov     rcx, [rbx]
0x18008aa10  mov     r8d, edi
0x18008aa13  mov     [rbx+50h], rax
0x18008aa17  mov     rax, cs:qword_1800AE638
0x18008aa1e  mov     rdx, [rdx+8]
0x18008aa22  mov     [rsp+58h+var_38], rsi
0x18008aa27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008aa2c  cmp     eax, 3E5h
0x18008aa31  jnz     loc_18008AAB8
0x18008aa37  mov     rcx, [rbx+50h]; hHandle
0x18008aa3b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18008aa3e  call    cs:__imp_WaitForSingleObject
0x18008aa45  nop     dword ptr [rax+rax+00h]
0x18008aa4a  mov     eax, [rsi]
0x18008aa4c  jmp     short loc_18008AAB8
0x18008aa4e  cmp     dword ptr [rbx+70h], 0
0x18008aa52  jnz     short loc_18008AAC2
0x18008aa54  cmp     qword ptr [rbx+10h], 0
0x18008aa59  jnz     short loc_18008AA62
0x18008aa5b  mov     eax, 6
0x18008aa60  jmp     short loc_18008AAB1
0x18008aa62  xor     edx, edx; Val
0x18008aa64  lea     rcx, [rbx+18h]; void *
0x18008aa68  lea     r8d, [rdx+50h]; Size
0x18008aa6c  call    memset_0
0x18008aa71  mov     rax, [rbx+68h]
0x18008aa75  lea     r8, [rbx+38h]
0x18008aa79  mov     rdx, [rbx+10h]
0x18008aa7d  mov     rcx, [rbx]
0x18008aa80  mov     [rbx+50h], rax
0x18008aa84  mov     rax, cs:qword_1800AE640
0x18008aa8b  mov     rdx, [rdx+8]
0x18008aa8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008aa94  cmp     eax, 3E5h
0x18008aa99  jnz     short loc_18008AAB1
0x18008aa9b  mov     rcx, [rbx+50h]; hHandle
0x18008aa9f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18008aaa2  call    cs:__imp_WaitForSingleObject
0x18008aaa9  nop     dword ptr [rax+rax+00h]
0x18008aaae  mov     eax, [rbx+38h]
0x18008aab1  mov     dword ptr [rbx+70h], 1
0x18008aab8  test    eax, eax
0x18008aaba  jz      short loc_18008AAC4
0x18008aabc  mov     [rbx+88h], eax
0x18008aac2  xor     eax, eax
0x18008aac4  add     rsp, 38h
0x18008aac8  pop     rdi
0x18008aac9  pop     rsi
0x18008aaca  pop     rbp
0x18008aacb  pop     rbx
0x18008aacc  retn
```
