# LRPC_SCALL::GetClientSid(void * *)

- ea: `0x180085440`
- end: `0x180085567`
- name: `?GetClientSid@LRPC_SCALL@@QEAAJPEAPEAX@Z`
- size: `295`
- prototype: `__int64 __fastcall(LRPC_SCALL *__hidden this, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180085070`

## callees

- `0x180021e70`
- `0x180022870`
- `0x18002f460`
- `0x18007200c`
- `0x180085440`
- `0x180085570`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008555a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008555a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800854e3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800854e3`

## pseudocode

```c
__int64 __fastcall LRPC_SCALL::GetClientSid(LRPC_SCALL *this, void **a2)
{
  bool v2; // zf
  __int64 result; // rax
  int v6; // eax
  unsigned int v7; // ebx
  SIZE_T v8; // rsi
  PSID *v9; // rdi
  void *v10; // rax
  void *v11; // rax
  DWORD ReturnLength; // [rsp+50h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  v2 = *((_QWORD *)this + 74) == 0;
  TokenHandle = 0;
  ReturnLength = 0;
  if ( !v2
    || (result = LRPC_ADDRESS::GetClientSid(
                   *(LRPC_ADDRESS **)(*((_QWORD *)this + 38) + 56LL),
                   *((struct _PORT_MESSAGE **)this + 55),
                   a2),
        (_DWORD)result) )
  {
    TokenHandle = 0;
    v6 = LRPC_SCALL::SaveClientToken(this, &TokenHandle);
    v7 = v6;
    if ( !v6 )
    {
      v8 = 64;
      while ( 1 )
      {
        v9 = (PSID *)AllocWrapper(v8);
        if ( !v9 )
          goto LABEL_9;
        if ( GetTokenInformation(TokenHandle, TokenUser, v9, v8, &ReturnLength) )
          break;
        if ( ReturnLength <= (unsigned int)v8 )
        {
          v7 = 5;
LABEL_14:
          FreeWrapper(v9);
          goto LABEL_18;
        }
        v8 = ReturnLength;
        FreeWrapper(v9);
      }
      v10 = DuplicateSID(*v9);
      if ( v10 )
        *a2 = v10;
      else
        v7 = 14;
      goto LABEL_14;
    }
    if ( v6 == 1347 )
    {
      v11 = DuplicateSID(&AnonymousSid);
      if ( v11 )
      {
        *a2 = v11;
        v7 = 0;
      }
      else
      {
LABEL_9:
        v7 = 14;
      }
    }
LABEL_18:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180085440  mov     [rsp+arg_8], rbx
0x180085445  push    rsi
0x180085446  push    rdi
0x180085447  push    r14
0x180085449  sub     rsp, 30h
0x18008544d  cmp     qword ptr [rcx+250h], 0
0x180085455  mov     r14, rdx
0x180085458  mov     rbx, rcx
0x18008545b  mov     [rsp+48h+TokenHandle], 0
0x180085464  mov     [rsp+48h+arg_0], 0
0x18008546c  jnz     short loc_18008549A
0x18008546e  mov     rcx, [rcx+130h]
0x180085475  mov     r8, rdx; void **
0x180085478  mov     rdx, [rbx+1B8h]; struct _PORT_MESSAGE *
0x18008547f  mov     rcx, [rcx+38h]; this
0x180085483  call    ?GetClientSid@LRPC_ADDRESS@@QEAAJPEAU_PORT_MESSAGE@@PEAPEAX@Z; LRPC_ADDRESS::GetClientSid(_PORT_MESSAGE *,void * *)
0x180085488  test    eax, eax
0x18008548a  jnz     short loc_18008549A
0x18008548c  mov     rbx, [rsp+48h+arg_8]
0x180085491  add     rsp, 30h
0x180085495  pop     r14
0x180085497  pop     rdi
0x180085498  pop     rsi
0x180085499  retn
0x18008549a  lea     rdx, [rsp+48h+TokenHandle]; void **
0x18008549f  mov     [rsp+48h+TokenHandle], 0
0x1800854a8  mov     rcx, rbx; this
0x1800854ab  call    ?SaveClientToken@LRPC_SCALL@@QEAAJPEAPEAX@Z; LRPC_SCALL::SaveClientToken(void * *)
0x1800854b0  mov     ebx, eax
0x1800854b2  test    eax, eax
0x1800854b4  jnz     short loc_180085533
0x1800854b6  lea     esi, [rax+40h]
0x1800854b9  mov     rcx, rsi; dwBytes
0x1800854bc  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800854c1  mov     rdi, rax
0x1800854c4  test    rax, rax
0x1800854c7  jz      short loc_180085501
0x1800854c9  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x1800854ce  lea     rax, [rsp+48h+arg_0]
0x1800854d3  mov     r9d, esi; TokenInformationLength
0x1800854d6  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800854db  mov     r8, rdi; TokenInformation
0x1800854de  mov     edx, 1; TokenInformationClass
0x1800854e3  call    cs:__imp_GetTokenInformation
0x1800854e9  test    eax, eax
0x1800854eb  jnz     short loc_18008550F
0x1800854ed  cmp     [rsp+48h+arg_0], esi
0x1800854f1  jbe     short loc_180085508
0x1800854f3  mov     esi, [rsp+48h+arg_0]
0x1800854f7  mov     rcx, rdi; lpMem
0x1800854fa  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800854ff  jmp     short loc_1800854B9
0x180085501  mov     ebx, 0Eh
0x180085506  jmp     short loc_180085550
0x180085508  mov     ebx, 5
0x18008550d  jmp     short loc_180085524
0x18008550f  mov     rcx, [rdi]; pSourceSid
0x180085512  call    ?DuplicateSID@@YAPEAXQEAX@Z; DuplicateSID(void * const)
0x180085517  test    rax, rax
0x18008551a  jnz     short loc_180085521
0x18008551c  lea     ebx, [rax+0Eh]
0x18008551f  jmp     short loc_180085524
0x180085521  mov     [r14], rax
0x180085524  test    rdi, rdi
0x180085527  jz      short loc_180085550
0x180085529  mov     rcx, rdi; lpMem
0x18008552c  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180085531  jmp     short loc_180085550
0x180085533  cmp     eax, 543h
0x180085538  jnz     short loc_180085550
0x18008553a  lea     rcx, ?AnonymousSid@@3U_SID@@B; pSourceSid
0x180085541  call    ?DuplicateSID@@YAPEAXQEAX@Z; DuplicateSID(void * const)
0x180085546  test    rax, rax
0x180085549  jz      short loc_180085501
0x18008554b  mov     [r14], rax
0x18008554e  xor     ebx, ebx
0x180085550  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180085555  test    rcx, rcx
0x180085558  jz      short loc_180085560
0x18008555a  call    cs:__imp_CloseHandle
0x180085560  mov     eax, ebx
0x180085562  jmp     loc_18008548C
```
