# GetClientToken(int,void * *)

- ea: `0x180161378`
- end: `0x1801614ec`
- name: `?GetClientToken@@YAKHPEAPEAX@Z`
- size: `372`
- prototype: `unsigned int __fastcall(int, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1801268e0`
- `0x180126c70`
- `0x1801627b0`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180161378`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016141f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016141f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801613fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801613fe`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180161415`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180161415`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18016149d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18016149d`
- `RPCRT4!RpcImpersonateClient` at `0x1801613c7`
- `RPCRT4!RpcImpersonateClient` at `0x1801613c7`
- `RPCRT4!RpcRevertToSelf` at `0x180161451`
- `RPCRT4!RpcRevertToSelf` at `0x180161451`

## pseudocode

```c
__int64 __fastcall GetClientToken(__int64 a1, void **a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *v9; // rax
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  TokenHandle = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 29, WPP_e6253edaf4023fbc0336011795d1ecda_Traceguids);
  }
  v3 = RpcImpersonateClient(0);
  v4 = v3;
  if ( v3 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v6 = 30;
LABEL_20:
      WPP_SF_d(v5[12], v6, WPP_e6253edaf4023fbc0336011795d1ecda_Traceguids, v3);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 31, WPP_e6253edaf4023fbc0336011795d1ecda_Traceguids, LastError);
      }
    }
    v3 = RpcRevertToSelf();
    v4 = v3;
    if ( !v3 )
    {
      v9 = TokenHandle;
      v5 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_24;
    }
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v6 = 32;
      goto LABEL_20;
    }
  }
  v9 = TokenHandle;
  if ( !TokenHandle )
  {
LABEL_24:
    *a2 = v9;
    goto LABEL_25;
  }
  CloseHandle(TokenHandle);
  v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_25:
  if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 105) >= 4u && (*((_BYTE *)v5 + 108) & 1) != 0 )
    WPP_SF_d(v5[12], 33, WPP_e6253edaf4023fbc0336011795d1ecda_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180161378  push    rbx
0x18016137a  push    rbp
0x18016137b  push    rdi
0x18016137c  push    r14
0x18016137e  sub     rsp, 28h
0x180161382  mov     rdi, rdx
0x180161385  mov     [rsp+48h+TokenHandle], 0
0x18016138e  mov     rcx, cs:WPP_GLOBAL_Control
0x180161395  lea     rbp, WPP_GLOBAL_Control
0x18016139c  lea     r14, WPP_e6253edaf4023fbc0336011795d1ecda_Traceguids
0x1801613a3  cmp     rcx, rbp
0x1801613a6  jz      short loc_1801613C5
0x1801613a8  cmp     byte ptr [rcx+69h], 4
0x1801613ac  jb      short loc_1801613C5
0x1801613ae  test    byte ptr [rcx+6Ch], 1
0x1801613b2  jz      short loc_1801613C5
0x1801613b4  mov     rcx, [rcx+60h]
0x1801613b8  mov     edx, 1Dh
0x1801613bd  mov     r8, r14
0x1801613c0  call    WPP_SF_
0x1801613c5  xor     ecx, ecx; BindingHandle
0x1801613c7  call    cs:__imp_RpcImpersonateClient
0x1801613cd  mov     ebx, eax
0x1801613cf  test    eax, eax
0x1801613d1  jz      short loc_1801613FE
0x1801613d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801613da  cmp     rcx, rbp
0x1801613dd  jz      loc_180161490
0x1801613e3  cmp     byte ptr [rcx+69h], 1
0x1801613e7  jb      loc_180161490
0x1801613ed  test    byte ptr [rcx+6Ch], 1
0x1801613f1  jz      loc_180161490
0x1801613f7  mov     edx, 1Eh
0x1801613fc  jmp     short loc_18016147A
0x1801613fe  call    cs:__imp_GetCurrentThread
0x180161404  mov     edx, 0Eh; DesiredAccess
0x180161409  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18016140e  mov     rcx, rax; ThreadHandle
0x180161411  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x180161415  call    cs:__imp_OpenThreadToken
0x18016141b  test    eax, eax
0x18016141d  jnz     short loc_180161451
0x18016141f  call    cs:__imp_GetLastError
0x180161425  mov     rcx, cs:WPP_GLOBAL_Control
0x18016142c  cmp     rcx, rbp
0x18016142f  jz      short loc_180161451
0x180161431  cmp     byte ptr [rcx+69h], 1
0x180161435  jb      short loc_180161451
0x180161437  test    byte ptr [rcx+6Ch], 1
0x18016143b  jz      short loc_180161451
0x18016143d  mov     rcx, [rcx+60h]
0x180161441  mov     edx, 1Fh
0x180161446  mov     r9d, eax
0x180161449  mov     r8, r14
0x18016144c  call    WPP_SF_d
0x180161451  call    cs:__imp_RpcRevertToSelf
0x180161457  mov     ebx, eax
0x180161459  test    eax, eax
0x18016145b  jz      short loc_1801614AC
0x18016145d  mov     rcx, cs:WPP_GLOBAL_Control
0x180161464  cmp     rcx, rbp
0x180161467  jz      short loc_180161490
0x180161469  cmp     byte ptr [rcx+69h], 1
0x18016146d  jb      short loc_180161490
0x18016146f  test    byte ptr [rcx+6Ch], 1
0x180161473  jz      short loc_180161490
0x180161475  mov     edx, 20h ; ' '
0x18016147a  mov     rcx, [rcx+60h]
0x18016147e  mov     r9d, eax
0x180161481  mov     r8, r14
0x180161484  call    WPP_SF_d
0x180161489  mov     rcx, cs:WPP_GLOBAL_Control
0x180161490  mov     rax, [rsp+48h+TokenHandle]
0x180161495  test    rax, rax
0x180161498  jz      short loc_1801614B8
0x18016149a  mov     rcx, rax; hObject
0x18016149d  call    cs:__imp_CloseHandle
0x1801614a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801614aa  jmp     short loc_1801614BB
0x1801614ac  mov     rax, [rsp+48h+TokenHandle]
0x1801614b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1801614b8  mov     [rdi], rax
0x1801614bb  cmp     rcx, rbp
0x1801614be  jz      short loc_1801614E0
0x1801614c0  cmp     byte ptr [rcx+69h], 4
0x1801614c4  jb      short loc_1801614E0
0x1801614c6  test    byte ptr [rcx+6Ch], 1
0x1801614ca  jz      short loc_1801614E0
0x1801614cc  mov     rcx, [rcx+60h]
0x1801614d0  mov     edx, 21h ; '!'
0x1801614d5  mov     r9d, ebx
0x1801614d8  mov     r8, r14
0x1801614db  call    WPP_SF_d
0x1801614e0  mov     eax, ebx
0x1801614e2  add     rsp, 28h
0x1801614e6  pop     r14
0x1801614e8  pop     rdi
0x1801614e9  pop     rbp
0x1801614ea  pop     rbx
0x1801614eb  retn
```
