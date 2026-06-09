# HTTP_LOG_PIPE_CLIENT::Initialize(char const *)

- ea: `0x1800097f8`
- end: `0x1800099ae`
- name: `?Initialize@HTTP_LOG_PIPE_CLIENT@@QEAAJPEBD@Z`
- size: `438`
- prototype: `__int64 __fastcall(_QWORD *pv, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000b964`

## callees

- `0x1800097f8`
- `0x180009c84`
- `0x18000e97a`
- `0x18000e9a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098ca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800098b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800098b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009943`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009943`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009982`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009982`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800098ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800098ee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180009960`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180009960`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000989e`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000989e`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180009884`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180009884`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_PIPE_CLIENT::Initialize(_QWORD *pv, char *a2)
{
  signed int v4; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rax
  __int64 v8; // r8
  void *v9; // rcx
  struct _TP_WAIT *v10; // rcx
  void **v12; // [rsp+20h] [rbp-29h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-21h]
  unsigned int v14; // [rsp+30h] [rbp-19h]
  size_t Size; // [rsp+34h] [rbp-15h]
  _BYTE v16[64]; // [rsp+3Ch] [rbp-Dh] BYREF
  __int16 v17; // [rsp+7Ch] [rbp+33h]

  v12 = &STBUFF::`vftable';
  hMem = v16;
  v14 = 0;
  Size = 0x400000000040LL;
  memset_0(v16, 0, sizeof(v16));
  v17 = 0;
  v4 = STRA::Copy((STRA *)(pv + 28), a2);
  if ( v4 >= 0 )
  {
    v4 = STRU::CopyA((STRU *)(pv + 35), a2);
    if ( v4 >= 0 )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      pv[24] = EventW;
      if ( !EventW
        || (ThreadpoolWait = CreateThreadpoolWait(HTTP_LOG_PIPE_CLIENT::SrvProcessWaitCallback, pv, 0),
            (pv[22] = ThreadpoolWait) == 0) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
LABEL_11:
        if ( v4 >= 0 )
          goto LABEL_16;
        goto LABEL_12;
      }
      v8 = -1;
      do
        ++v8;
      while ( a2[v8] );
      v4 = STBUFF::SetData((STBUFF *)&v12, a2, v8);
      if ( v4 >= 0 )
      {
        v4 = STBUFF::SetData((STBUFF *)(pv + 4), hMem, v14);
        goto LABEL_11;
      }
    }
  }
LABEL_12:
  v9 = (void *)pv[24];
  if ( v9 )
  {
    CloseHandle(v9);
    pv[24] = 0;
  }
  v10 = (struct _TP_WAIT *)pv[22];
  if ( v10 )
  {
    CloseThreadpoolWait(v10);
    pv[22] = 0;
  }
LABEL_16:
  v12 = &STBUFF::`vftable';
  if ( hMem != v16 )
    LocalFree(hMem);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800097f8  mov     [rsp-8+arg_10], rbx
0x1800097fd  mov     [rsp-8+arg_18], rsi
0x180009802  push    rbp
0x180009803  push    rdi
0x180009804  push    r15
0x180009806  lea     rbp, [rsp-47h]
0x18000980b  sub     rsp, 90h
0x180009812  mov     rax, cs:__security_cookie
0x180009819  xor     rax, rsp
0x18000981c  mov     [rbp+57h+var_20], rax
0x180009820  mov     rsi, rdx
0x180009823  mov     rdi, rcx
0x180009826  lea     r15, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x18000982d  mov     [rbp+57h+var_80], r15
0x180009831  lea     rax, [rbp+57h+var_64]
0x180009835  mov     [rbp+57h+hMem], rax
0x180009839  mov     [rbp+57h+var_70], 0
0x180009840  mov     r8d, 40h ; '@'; Size
0x180009846  mov     dword ptr [rbp+57h+Size], r8d
0x18000984a  mov     dword ptr [rbp+57h+Size+4], 4000h
0x180009851  xor     edx, edx; Val
0x180009853  lea     rcx, [rbp+57h+var_64]; void *
0x180009857  call    memset_0
0x18000985c  lea     rax, [rbp+57h+var_64]
0x180009860  mov     rcx, [rbp+57h+hMem]; void *
0x180009864  cmp     rcx, rax
0x180009867  jz      short loc_180009874
0x180009869  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x18000986d  xor     edx, edx; Val
0x18000986f  call    memset_0
0x180009874  mov     [rbp+57h+var_24], 0
0x18000987a  lea     rcx, [rdi+0E0h]
0x180009881  mov     rdx, rsi
0x180009884  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000988a  mov     ebx, eax
0x18000988c  test    eax, eax
0x18000988e  js      loc_180009937
0x180009894  lea     rcx, [rdi+118h]
0x18000989b  mov     rdx, rsi
0x18000989e  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x1800098a4  mov     ebx, eax
0x1800098a6  test    eax, eax
0x1800098a8  js      loc_180009937
0x1800098ae  xor     r9d, r9d; lpName
0x1800098b1  xor     r8d, r8d; bInitialState
0x1800098b4  xor     edx, edx; bManualReset
0x1800098b6  xor     ecx, ecx; lpEventAttributes
0x1800098b8  call    cs:__imp_CreateEventW
0x1800098be  mov     [rdi+0C0h], rax
0x1800098c5  test    rax, rax
0x1800098c8  jnz     short loc_1800098E1
0x1800098ca  call    cs:__imp_GetLastError
0x1800098d0  mov     ebx, eax
0x1800098d2  test    eax, eax
0x1800098d4  jle     short loc_180009933
0x1800098d6  movzx   ebx, ax
0x1800098d9  or      ebx, 80070000h
0x1800098df  jmp     short loc_180009933
0x1800098e1  xor     r8d, r8d; pcbe
0x1800098e4  mov     rdx, rdi; pv
0x1800098e7  lea     rcx, ?SrvProcessWaitCallback@HTTP_LOG_PIPE_CLIENT@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800098ee  call    cs:__imp_CreateThreadpoolWait
0x1800098f4  mov     [rdi+0B0h], rax
0x1800098fb  test    rax, rax
0x1800098fe  jz      short loc_1800098CA
0x180009900  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009904  inc     r8; unsigned int
0x180009907  cmp     byte ptr [rsi+r8], 0
0x18000990c  jnz     short loc_180009904
0x18000990e  mov     rdx, rsi; void *
0x180009911  lea     rcx, [rbp+57h+var_80]; this
0x180009915  call    ?SetData@STBUFF@@QEAAJPEAXK@Z; STBUFF::SetData(void *,ulong)
0x18000991a  mov     ebx, eax
0x18000991c  test    eax, eax
0x18000991e  js      short loc_180009937
0x180009920  lea     rcx, [rdi+20h]; this
0x180009924  mov     r8d, [rbp+57h+var_70]; unsigned int
0x180009928  mov     rdx, [rbp+57h+hMem]; void *
0x18000992c  call    ?SetData@STBUFF@@QEAAJPEAXK@Z; STBUFF::SetData(void *,ulong)
0x180009931  mov     ebx, eax
0x180009933  test    ebx, ebx
0x180009935  jns     short loc_180009971
0x180009937  mov     rcx, [rdi+0C0h]; hObject
0x18000993e  test    rcx, rcx
0x180009941  jz      short loc_180009954
0x180009943  call    cs:__imp_CloseHandle
0x180009949  mov     qword ptr [rdi+0C0h], 0
0x180009954  mov     rcx, [rdi+0B0h]; pwa
0x18000995b  test    rcx, rcx
0x18000995e  jz      short loc_180009971
0x180009960  call    cs:__imp_CloseThreadpoolWait
0x180009966  mov     qword ptr [rdi+0B0h], 0
0x180009971  mov     [rbp+57h+var_80], r15
0x180009975  lea     rax, [rbp+57h+var_64]
0x180009979  mov     rcx, [rbp+57h+hMem]; hMem
0x18000997d  cmp     rcx, rax
0x180009980  jz      short loc_180009988
0x180009982  call    cs:__imp_LocalFree
0x180009988  mov     eax, ebx
0x18000998a  mov     rcx, [rbp+57h+var_20]
0x18000998e  xor     rcx, rsp; StackCookie
0x180009991  call    __security_check_cookie
0x180009996  lea     r11, [rsp+0A0h+var_10]
0x18000999e  mov     rbx, [r11+30h]
0x1800099a2  mov     rsi, [r11+38h]
0x1800099a6  mov     rsp, r11
0x1800099a9  pop     r15
0x1800099ab  pop     rdi
0x1800099ac  pop     rbp
0x1800099ad  retn
```
