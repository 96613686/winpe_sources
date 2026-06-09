# BaseHttpListener::SpawnWorkerThread(_HTTP_REQUEST_V2 *,void *)

- ea: `0x180031280`
- end: `0x1800313b0`
- name: `?SpawnWorkerThread@BaseHttpListener@@IEAAJPEAU_HTTP_REQUEST_V2@@PEAX@Z`
- size: `304`
- prototype: `__int64 __fastcall(BaseHttpListener *__hidden this, struct _HTTP_REQUEST_V2 *Block, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180030bac`

## callees

- `0x180021c04`
- `0x1800242a4`
- `0x1800255a8`
- `0x180028000`
- `0x180031280`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031312`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031356`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003135f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031312`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031356`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003135f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800312d5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800312d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031377`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180031340`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180031340`

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
0x180031280  push    rbx
0x180031282  push    rbp
0x180031283  push    rsi
0x180031284  push    rdi
0x180031285  push    r12
0x180031287  push    r14
0x180031289  push    r15
0x18003128b  sub     rsp, 20h
0x18003128f  mov     r15, r8
0x180031292  mov     rbp, rdx
0x180031295  mov     r14, rcx
0x180031298  mov     rbx, cs:WPP_GLOBAL_Control
0x18003129f  lea     r12, WPP_GLOBAL_Control
0x1800312a6  cmp     rbx, r12
0x1800312a9  jz      short loc_1800312D0
0x1800312ab  test    dword ptr [rbx+1Ch], 100h
0x1800312b2  jz      short loc_1800312D0
0x1800312b4  mov     rcx, [rbx+10h]
0x1800312b8  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800312bf  mov     edx, 73h ; 's'
0x1800312c4  call    WPP_SF_
0x1800312c9  mov     rbx, cs:WPP_GLOBAL_Control
0x1800312d0  mov     ecx, 18h; Size
0x1800312d5  call    cs:__imp_malloc
0x1800312db  mov     rdi, rax
0x1800312de  test    rax, rax
0x1800312e1  jnz     short loc_18003131D
0x1800312e3  mov     esi, 8007000Eh
0x1800312e8  cmp     rbx, r12
0x1800312eb  jz      short loc_180031306
0x1800312ed  test    byte ptr [rbx+1Ch], 1
0x1800312f1  jz      short loc_180031306
0x1800312f3  mov     rcx, [rbx+10h]
0x1800312f7  lea     edx, [rax+74h]
0x1800312fa  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180031301  call    WPP_SF_
0x180031306  test    rbp, rbp
0x180031309  jz      loc_18003139F
0x18003130f  mov     rcx, rbp; Block
0x180031312  call    cs:__imp_free
0x180031318  jmp     loc_18003139F
0x18003131d  mov     rcx, r14; this
0x180031320  mov     [rax], r14
0x180031323  xor     esi, esi
0x180031325  mov     [rax+8], r15
0x180031329  mov     [rax+10h], rbp
0x18003132d  call    ?IncrThreadCount@BaseHttpListener@@IEAAXXZ; BaseHttpListener::IncrThreadCount(void)
0x180031332  lea     r8d, [rsi+10h]; Flags
0x180031336  mov     rdx, rdi; Context
0x180031339  lea     rcx, ?HandleHTTPRequestWrapperStub@BaseHttpListener@@KAKPEAX@Z; Function
0x180031340  call    cs:__imp_QueueUserWorkItem
0x180031346  test    eax, eax
0x180031348  jnz     short loc_18003139F
0x18003134a  mov     rcx, r14; this
0x18003134d  call    ?DecrThreadCount@BaseHttpListener@@IEAAXXZ; BaseHttpListener::DecrThreadCount(void)
0x180031352  mov     rcx, [rdi+10h]; Block
0x180031356  call    cs:__imp_free
0x18003135c  mov     rcx, rdi; Block
0x18003135f  call    cs:__imp_free
0x180031365  mov     rax, cs:WPP_GLOBAL_Control
0x18003136c  cmp     rax, r12
0x18003136f  jz      short loc_18003139A
0x180031371  test    byte ptr [rax+1Ch], 1
0x180031375  jz      short loc_18003139A
0x180031377  call    cs:__imp_GetLastError
0x18003137d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031384  lea     edx, [rsi+75h]
0x180031387  mov     r9d, eax
0x18003138a  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180031391  mov     rcx, [rcx+10h]
0x180031395  call    WPP_SF_d
0x18003139a  mov     esi, 80004005h
0x18003139f  mov     eax, esi
0x1800313a1  add     rsp, 20h
0x1800313a5  pop     r15
0x1800313a7  pop     r14
0x1800313a9  pop     r12
0x1800313ab  pop     rdi
0x1800313ac  pop     rsi
0x1800313ad  pop     rbp
0x1800313ae  pop     rbx
0x1800313af  retn
```
