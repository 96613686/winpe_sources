# BaseHttpListener::SpawnWorkerThread(_HTTP_REQUEST_V2 *,void *)

- ea: `0x180033a88`
- end: `0x180033bdd`
- name: `?SpawnWorkerThread@BaseHttpListener@@IEAAJPEAU_HTTP_REQUEST_V2@@PEAX@Z`
- size: `341`
- prototype: `__int64 __fastcall(BaseHttpListener *__hidden this, struct _HTTP_REQUEST_V2 *Block, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800332c8`

## callees

- `0x1800234d8`
- `0x180025d44`
- `0x1800271fc`
- `0x180029df0`
- `0x180033a88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033b20`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033b70`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033b7f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033b20`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033b70`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180033b7f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180033add`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180033add`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b9d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180033b54`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180033b54`

## pseudocode

```c
__int64 __fastcall BaseHttpListener::SpawnWorkerThread(
        BaseHttpListener *this,
        struct _HTTP_REQUEST_V2 *Block,
        void *a3)
{
  LPCSTR v6; // rbx
  void **v7; // rax
  void **v8; // rdi
  unsigned int v9; // esi
  DWORD LastError; // eax

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = (void **)malloc(0x18u);
  v8 = v7;
  if ( v7 )
  {
    *v7 = this;
    v9 = 0;
    v7[1] = a3;
    v7[2] = Block;
    BaseHttpListener::IncrThreadCount(this);
    if ( !QueueUserWorkItem(BaseHttpListener::HandleHTTPRequestWrapperStub, v8, 0x10u) )
    {
      BaseHttpListener::DecrThreadCount(this);
      free(v8[2]);
      free(v8);
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, LastError);
      }
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    v9 = -2147024882;
    if ( v6 != (LPCSTR)&WPP_GLOBAL_Control && (v6[28] & 1) != 0 )
      WPP_SF_(*((_QWORD *)v6 + 2), 116, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
    if ( Block )
      free(Block);
  }
  return v9;
}

```

## disassembly

```asm
0x180033a88  push    rbx
0x180033a8a  push    rbp
0x180033a8b  push    rsi
0x180033a8c  push    rdi
0x180033a8d  push    r12
0x180033a8f  push    r14
0x180033a91  push    r15
0x180033a93  sub     rsp, 20h
0x180033a97  mov     r15, r8
0x180033a9a  mov     rbp, rdx
0x180033a9d  mov     r14, rcx
0x180033aa0  mov     rbx, cs:WPP_GLOBAL_Control
0x180033aa7  lea     r12, WPP_GLOBAL_Control
0x180033aae  cmp     rbx, r12
0x180033ab1  jz      short loc_180033AD8
0x180033ab3  test    dword ptr [rbx+1Ch], 100h
0x180033aba  jz      short loc_180033AD8
0x180033abc  mov     rcx, [rbx+10h]
0x180033ac0  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180033ac7  mov     edx, 73h ; 's'
0x180033acc  call    WPP_SF_
0x180033ad1  mov     rbx, cs:WPP_GLOBAL_Control
0x180033ad8  mov     ecx, 18h; Size
0x180033add  call    cs:__imp_malloc
0x180033ae4  nop     dword ptr [rax+rax+00h]
0x180033ae9  mov     rdi, rax
0x180033aec  test    rax, rax
0x180033aef  jnz     short loc_180033B31
0x180033af1  mov     esi, 8007000Eh
0x180033af6  cmp     rbx, r12
0x180033af9  jz      short loc_180033B14
0x180033afb  test    byte ptr [rbx+1Ch], 1
0x180033aff  jz      short loc_180033B14
0x180033b01  mov     rcx, [rbx+10h]
0x180033b05  lea     edx, [rax+74h]
0x180033b08  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180033b0f  call    WPP_SF_
0x180033b14  test    rbp, rbp
0x180033b17  jz      loc_180033BCB
0x180033b1d  mov     rcx, rbp; Block
0x180033b20  call    cs:__imp_free
0x180033b27  nop     dword ptr [rax+rax+00h]
0x180033b2c  jmp     loc_180033BCB
0x180033b31  mov     rcx, r14; this
0x180033b34  mov     [rax], r14
0x180033b37  xor     esi, esi
0x180033b39  mov     [rax+8], r15
0x180033b3d  mov     [rax+10h], rbp
0x180033b41  call    ?IncrThreadCount@BaseHttpListener@@IEAAXXZ; BaseHttpListener::IncrThreadCount(void)
0x180033b46  lea     r8d, [rsi+10h]; Flags
0x180033b4a  mov     rdx, rdi; Context
0x180033b4d  lea     rcx, ?HandleHTTPRequestWrapperStub@BaseHttpListener@@KAKPEAX@Z; Function
0x180033b54  call    cs:__imp_QueueUserWorkItem
0x180033b5b  nop     dword ptr [rax+rax+00h]
0x180033b60  test    eax, eax
0x180033b62  jnz     short loc_180033BCB
0x180033b64  mov     rcx, r14; this
0x180033b67  call    ?DecrThreadCount@BaseHttpListener@@IEAAXXZ; BaseHttpListener::DecrThreadCount(void)
0x180033b6c  mov     rcx, [rdi+10h]; Block
0x180033b70  call    cs:__imp_free
0x180033b77  nop     dword ptr [rax+rax+00h]
0x180033b7c  mov     rcx, rdi; Block
0x180033b7f  call    cs:__imp_free
0x180033b86  nop     dword ptr [rax+rax+00h]
0x180033b8b  mov     rax, cs:WPP_GLOBAL_Control
0x180033b92  cmp     rax, r12
0x180033b95  jz      short loc_180033BC6
0x180033b97  test    byte ptr [rax+1Ch], 1
0x180033b9b  jz      short loc_180033BC6
0x180033b9d  call    cs:__imp_GetLastError
0x180033ba4  nop     dword ptr [rax+rax+00h]
0x180033ba9  mov     rcx, cs:WPP_GLOBAL_Control
0x180033bb0  lea     edx, [rsi+75h]
0x180033bb3  mov     r9d, eax
0x180033bb6  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180033bbd  mov     rcx, [rcx+10h]
0x180033bc1  call    WPP_SF_d
0x180033bc6  mov     esi, 80004005h
0x180033bcb  mov     eax, esi
0x180033bcd  add     rsp, 20h
0x180033bd1  pop     r15
0x180033bd3  pop     r14
0x180033bd5  pop     r12
0x180033bd7  pop     rdi
0x180033bd8  pop     rsi
0x180033bd9  pop     rbp
0x180033bda  pop     rbx
0x180033bdb  retn
```
