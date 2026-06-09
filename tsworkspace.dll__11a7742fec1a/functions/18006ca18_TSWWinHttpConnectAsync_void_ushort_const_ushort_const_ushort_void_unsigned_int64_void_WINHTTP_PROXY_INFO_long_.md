# TSWWinHttpConnectAsync(void *,ushort const *,ushort const *,ushort,void (*)(unsigned __int64,void *,_WINHTTP_PROXY_INFO &,long),unsigned __int64)

- ea: `0x18006ca18`
- end: `0x18006cb50`
- name: `?TSWWinHttpConnectAsync@@YAP6AX_KPEAXAEAU_WINHTTP_PROXY_INFO@@J@Z1PEBG3GP6AX012J@Z0@Z`
- size: `312`
- prototype: `void (*__fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16, void (*)(unsigned __int64, void *, struct _WINHTTP_PROXY_INFO *, int), unsigned __int64))(unsigned __int64, void *, struct _WINHTTP_PROXY_INFO *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180059490`

## callees

- `0x1800034b8`
- `0x180004970`
- `0x18000dbdc`
- `0x18006c814`
- `0x18006ca18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cb0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cb0c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18006cb01`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18006cb01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cb26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cb26`
- `KERNEL32!SetLastError` at `0x18006cb33`
- `KERNEL32!SetLastError` at `0x18006cb33`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void (__fastcall *__fastcall TSWWinHttpConnectAsync(
        void *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int16 a4,
        void (*a5)(unsigned __int64, void *, struct _WINHTTP_PROXY_INFO *, int),
        unsigned __int64 a6))(struct DM_CONNECT_CONTEXT *, void *, struct _WINHTTP_PROXY_INFO *, int)
{
  char *v10; // rax
  _QWORD *v11; // rbx
  DWORD v12; // ecx
  void (__fastcall *v13)(struct DM_CONNECT_CONTEXT *, void *, struct _WINHTTP_PROXY_INFO *, int); // rdi
  HANDLE Thread; // rax
  unsigned int v15; // edx

  if ( !a1 || !a2 || !a3 || !a4 || !a6 )
  {
    v12 = 87;
    goto LABEL_16;
  }
  v10 = (char *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    std::wstring::wstring(v10 + 16);
    std::wstring::wstring(v11 + 6);
  }
  else
  {
    v11 = 0;
  }
  if ( !v11 )
  {
    v12 = 14;
LABEL_16:
    SetLastError(v12);
    return 0;
  }
  v13 = CDownloadManager::TSWWinHttpConnectCallbackFn;
  *v11 = a6;
  v11[1] = a1;
  std::wstring::assign(v11 + 2, a2);
  std::wstring::assign(v11 + 6, a3);
  *((_WORD *)v11 + 40) = a4;
  v11[11] = CDownloadManager::TSWWinHttpConnectCallbackFn;
  Thread = CreateThread(0, 0, TSWWinHttpConnectThreadProc, v11, 0, 0);
  if ( Thread )
  {
    CloseHandle(Thread);
  }
  else if ( GetLastError() )
  {
    v13 = 0;
    TS_WORKSPACE_CONNECT_STATE::`scalar deleting destructor'((TS_WORKSPACE_CONNECT_STATE *)v11, v15);
  }
  return v13;
}

```

## disassembly

```asm
0x18006ca18  push    rbx
0x18006ca1a  push    rbp
0x18006ca1b  push    rsi
0x18006ca1c  push    rdi
0x18006ca1d  push    r12
0x18006ca1f  push    r13
0x18006ca21  push    r14
0x18006ca23  push    r15
0x18006ca25  sub     rsp, 48h
0x18006ca29  mov     [rsp+88h+var_58], 0FFFFFFFFFFFFFFFEh
0x18006ca32  movzx   ebp, r9w
0x18006ca36  mov     r14, r8
0x18006ca39  mov     r15, rdx
0x18006ca3c  mov     r12, rcx
0x18006ca3f  xor     r13d, r13d
0x18006ca42  test    rcx, rcx
0x18006ca45  jz      loc_18006CB2E
0x18006ca4b  test    rdx, rdx
0x18006ca4e  jz      loc_18006CB2E
0x18006ca54  test    r8, r8
0x18006ca57  jz      loc_18006CB2E
0x18006ca5d  test    r9w, r9w
0x18006ca61  jz      loc_18006CB2E
0x18006ca67  mov     rsi, [rsp+88h+arg_28]
0x18006ca6f  test    rsi, rsi
0x18006ca72  jz      loc_18006CB2E
0x18006ca78  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006ca7f  lea     ecx, [r13+60h]; unsigned __int64
0x18006ca83  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006ca88  mov     rbx, rax
0x18006ca8b  mov     [rsp+88h+arg_0], rax
0x18006ca93  test    rax, rax
0x18006ca96  jz      short loc_18006CAAE
0x18006ca98  lea     rcx, [rax+10h]
0x18006ca9c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006caa1  nop
0x18006caa2  lea     rcx, [rbx+30h]
0x18006caa6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18006caab  nop
0x18006caac  jmp     short loc_18006CAB1
0x18006caae  mov     rbx, r13
0x18006cab1  test    rbx, rbx
0x18006cab4  jnz     short loc_18006CABB
0x18006cab6  lea     ecx, [rbx+0Eh]
0x18006cab9  jmp     short loc_18006CB33
0x18006cabb  lea     rdi, ?TSWWinHttpConnectCallbackFn@CDownloadManager@@KAX_KPEAXAEAU_WINHTTP_PROXY_INFO@@J@Z; CDownloadManager::TSWWinHttpConnectCallbackFn(unsigned __int64,void *,_WINHTTP_PROXY_INFO &,long)
0x18006cac2  mov     [rbx], rsi
0x18006cac5  mov     [rbx+8], r12
0x18006cac9  lea     rcx, [rbx+10h]
0x18006cacd  mov     rdx, r15
0x18006cad0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18006cad5  lea     rcx, [rbx+30h]
0x18006cad9  mov     rdx, r14
0x18006cadc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18006cae1  mov     [rbx+50h], bp
0x18006cae5  mov     [rbx+58h], rdi
0x18006cae9  mov     [rsp+88h+lpThreadId], r13; lpThreadId
0x18006caee  mov     [rsp+88h+dwCreationFlags], r13d; dwCreationFlags
0x18006caf3  mov     r9, rbx; lpParameter
0x18006caf6  lea     r8, ?TSWWinHttpConnectThreadProc@@YAKPEAX@Z; lpStartAddress
0x18006cafd  xor     edx, edx; dwStackSize
0x18006caff  xor     ecx, ecx; lpThreadAttributes
0x18006cb01  call    cs:__imp_CreateThread
0x18006cb07  test    rax, rax
0x18006cb0a  jnz     short loc_18006CB23
0x18006cb0c  call    cs:__imp_GetLastError
0x18006cb12  test    eax, eax
0x18006cb14  jz      short loc_18006CB3C
0x18006cb16  mov     rdi, r13
0x18006cb19  mov     rcx, rbx; this
0x18006cb1c  call    ??_GTS_WORKSPACE_CONNECT_STATE@@QEAAPEAXI@Z; TS_WORKSPACE_CONNECT_STATE::`scalar deleting destructor'(uint)
0x18006cb21  jmp     short loc_18006CB3C
0x18006cb23  mov     rcx, rax; hObject
0x18006cb26  call    cs:__imp_CloseHandle
0x18006cb2c  jmp     short loc_18006CB3C
0x18006cb2e  mov     ecx, 57h ; 'W'; dwErrCode
0x18006cb33  call    cs:__imp_SetLastError
0x18006cb39  mov     rdi, r13
0x18006cb3c  mov     rax, rdi
0x18006cb3f  add     rsp, 48h
0x18006cb43  pop     r15
0x18006cb45  pop     r14
0x18006cb47  pop     r13
0x18006cb49  pop     r12
0x18006cb4b  pop     rdi
0x18006cb4c  pop     rsi
0x18006cb4d  pop     rbp
0x18006cb4e  pop     rbx
0x18006cb4f  retn
```
