# LRPC_SCALL::GetClientSid(void * *)

- ea: `0x180087400`
- end: `0x180087538`
- name: `?GetClientSid@LRPC_SCALL@@QEAAJPEAPEAX@Z`
- size: `312`
- prototype: `__int64 __fastcall(LRPC_SCALL *__hidden this, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180087000`

## callees

- `0x180023020`
- `0x180023a40`
- `0x1800307e0`
- `0x180070fec`
- `0x180087400`
- `0x180087540`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087525`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087525`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800874a8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800874a8`

## pseudocode

```c
__int64 __fastcall LRPC_SCALL::GetClientSid(LRPC_SCALL *this, void **a2)
{
  bool v2; // zf
  __int64 result; // rax
  unsigned int v6; // eax
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
0x180087400  mov     [rsp+arg_8], rbx
0x180087405  push    rsi
0x180087406  push    rdi
0x180087407  push    r14
0x180087409  sub     rsp, 30h
0x18008740d  cmp     qword ptr [rcx+250h], 0
0x180087415  mov     r14, rdx
0x180087418  mov     rbx, rcx
0x18008741b  mov     [rsp+48h+TokenHandle], 0
0x180087424  mov     [rsp+48h+arg_0], 0
0x18008742c  jnz     short loc_18008745B
0x18008742e  mov     rcx, [rcx+130h]
0x180087435  mov     r8, rdx; void **
0x180087438  mov     rdx, [rbx+1B8h]; struct _PORT_MESSAGE *
0x18008743f  mov     rcx, [rcx+38h]; this
0x180087443  call    ?GetClientSid@LRPC_ADDRESS@@QEAAJPEAU_PORT_MESSAGE@@PEAPEAX@Z; LRPC_ADDRESS::GetClientSid(_PORT_MESSAGE *,void * *)
0x180087448  test    eax, eax
0x18008744a  jnz     short loc_18008745B
0x18008744c  mov     rbx, [rsp+48h+arg_8]
0x180087451  add     rsp, 30h
0x180087455  pop     r14
0x180087457  pop     rdi
0x180087458  pop     rsi
0x180087459  retn
0x18008745b  lea     rdx, [rsp+48h+TokenHandle]; void **
0x180087460  mov     [rsp+48h+TokenHandle], 0
0x180087469  mov     rcx, rbx; this
0x18008746c  call    ?SaveClientToken@LRPC_SCALL@@QEAAJPEAPEAX@Z; LRPC_SCALL::SaveClientToken(void * *)
0x180087471  mov     ebx, eax
0x180087473  test    eax, eax
0x180087475  jnz     loc_1800874FE
0x18008747b  lea     esi, [rax+40h]
0x18008747e  mov     rcx, rsi; dwBytes
0x180087481  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180087486  mov     rdi, rax
0x180087489  test    rax, rax
0x18008748c  jz      short loc_1800874CC
0x18008748e  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180087493  lea     rax, [rsp+48h+arg_0]
0x180087498  mov     r9d, esi; TokenInformationLength
0x18008749b  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800874a0  mov     r8, rdi; TokenInformation
0x1800874a3  mov     edx, 1; TokenInformationClass
0x1800874a8  call    cs:__imp_GetTokenInformation
0x1800874af  nop     dword ptr [rax+rax+00h]
0x1800874b4  test    eax, eax
0x1800874b6  jnz     short loc_1800874DA
0x1800874b8  cmp     [rsp+48h+arg_0], esi
0x1800874bc  jbe     short loc_1800874D3
0x1800874be  mov     esi, [rsp+48h+arg_0]
0x1800874c2  mov     rcx, rdi; lpMem
0x1800874c5  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800874ca  jmp     short loc_18008747E
0x1800874cc  mov     ebx, 0Eh
0x1800874d1  jmp     short loc_18008751B
0x1800874d3  mov     ebx, 5
0x1800874d8  jmp     short loc_1800874EF
0x1800874da  mov     rcx, [rdi]; pSourceSid
0x1800874dd  call    ?DuplicateSID@@YAPEAXQEAX@Z; DuplicateSID(void * const)
0x1800874e2  test    rax, rax
0x1800874e5  jnz     short loc_1800874EC
0x1800874e7  lea     ebx, [rax+0Eh]
0x1800874ea  jmp     short loc_1800874EF
0x1800874ec  mov     [r14], rax
0x1800874ef  test    rdi, rdi
0x1800874f2  jz      short loc_18008751B
0x1800874f4  mov     rcx, rdi; lpMem
0x1800874f7  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800874fc  jmp     short loc_18008751B
0x1800874fe  cmp     eax, 543h
0x180087503  jnz     short loc_18008751B
0x180087505  lea     rcx, ?AnonymousSid@@3U_SID@@B; pSourceSid
0x18008750c  call    ?DuplicateSID@@YAPEAXQEAX@Z; DuplicateSID(void * const)
0x180087511  test    rax, rax
0x180087514  jz      short loc_1800874CC
0x180087516  mov     [r14], rax
0x180087519  xor     ebx, ebx
0x18008751b  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180087520  test    rcx, rcx
0x180087523  jz      short loc_180087531
0x180087525  call    cs:__imp_CloseHandle
0x18008752c  nop     dword ptr [rax+rax+00h]
0x180087531  mov     eax, ebx
0x180087533  jmp     loc_18008744C
```
