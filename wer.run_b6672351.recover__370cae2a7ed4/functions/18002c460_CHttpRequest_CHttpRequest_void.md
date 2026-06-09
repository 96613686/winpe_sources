# CHttpRequest::~CHttpRequest(void)

- ea: `0x18002c460`
- end: `0x18002c58b`
- name: `??1CHttpRequest@@QEAA@XZ`
- size: `299`
- prototype: `void __fastcall(CHttpRequest *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002feb4`
- `0x1800964dc`

## callees

- `0x180007fd8`
- `0x18000db80`
- `0x18002c460`
- `0x18003de9c`
- `0x18003e1ec`
- `0x180045388`
- `0x18004d78c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c521`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c531`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c541`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c521`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c531`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c541`

## pseudocode

```c
void __fastcall CHttpRequest::~CHttpRequest(CHttpRequest *this, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  char *v5; // rax

  if ( *((_QWORD *)this + 4) != -1 && *((_QWORD *)this + 4) != 0 )
    CHttpRequest::AbortRequest(this);
  if ( *(_QWORD *)this )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  if ( *((_QWORD *)this + 2) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  if ( *((_QWORD *)this + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  v4 = 520;
  v5 = (char *)this + 304;
  do
  {
    *v5++ = 0;
    --v4;
  }
  while ( v4 );
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 1000);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 968);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 936);
  utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>((char *)this + 912);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 880);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 832);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 272);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((char *)this + 192);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 48);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 32);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((char *)this + 24);
  tlx::unique_any<tlx::handle_traits<void *,int (*)(void *),&int WinHttpCloseHandle(void *),0>>::~unique_any<tlx::handle_traits<void *,int (*)(void *),&int WinHttpCloseHandle(void *),0>>((char *)this + 16);
  tlx::unique_any<tlx::handle_traits<void *,int (*)(void *),&int WinHttpCloseHandle(void *),0>>::~unique_any<tlx::handle_traits<void *,int (*)(void *),&int WinHttpCloseHandle(void *),0>>((char *)this + 8);
  tlx::unique_any<tlx::handle_traits<void *,int (*)(void *),&int WinHttpCloseHandle(void *),0>>::~unique_any<tlx::handle_traits<void *,int (*)(void *),&int WinHttpCloseHandle(void *),0>>(this);
}

```

## disassembly

```asm
0x18002c460  push    rbx
0x18002c462  push    rsi
0x18002c463  push    rdi
0x18002c464  push    r14
0x18002c466  sub     rsp, 28h
0x18002c46a  mov     rbx, rcx
0x18002c46d  mov     rax, [rcx+20h]
0x18002c471  inc     rax
0x18002c474  cmp     rax, 1
0x18002c478  jbe     short loc_18002C47F
0x18002c47a  call    ?AbortRequest@CHttpRequest@@QEAAXXZ; CHttpRequest::AbortRequest(void)
0x18002c47f  cmp     qword ptr [rbx], 0
0x18002c483  jz      short loc_18002C48A
0x18002c485  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002c48a  cmp     qword ptr [rbx+10h], 0
0x18002c48f  jz      short loc_18002C496
0x18002c491  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002c496  cmp     qword ptr [rbx+8], 0
0x18002c49b  jz      short loc_18002C4A2
0x18002c49d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002c4a2  mov     ecx, 208h
0x18002c4a7  lea     rax, [rbx+130h]
0x18002c4ae  mov     byte ptr [rax], 0
0x18002c4b1  inc     rax
0x18002c4b4  sub     rcx, 1
0x18002c4b8  jnz     short loc_18002C4AE
0x18002c4ba  lea     rcx, [rbx+3E8h]; void *
0x18002c4c1  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002c4c6  lea     rcx, [rbx+3C8h]; void *
0x18002c4cd  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002c4d2  lea     rcx, [rbx+3A8h]; void *
0x18002c4d9  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002c4de  lea     rcx, [rbx+390h]
0x18002c4e5  call    ??1?$unique_ptr@UIXmlWriter@@Urelease_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(void)
0x18002c4ea  lea     rcx, [rbx+370h]; void *
0x18002c4f1  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002c4f6  lea     rcx, [rbx+340h]; void *
0x18002c4fd  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002c502  lea     rcx, [rbx+110h]; void *
0x18002c509  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002c50e  lea     rcx, [rbx+0C0h]; void *
0x18002c515  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18002c51a  lea     rcx, [rbx+98h]; lpCriticalSection
0x18002c521  call    cs:__imp_DeleteCriticalSection
0x18002c528  nop     dword ptr [rax+rax+00h]
0x18002c52d  lea     rcx, [rbx+70h]; lpCriticalSection
0x18002c531  call    cs:__imp_DeleteCriticalSection
0x18002c538  nop     dword ptr [rax+rax+00h]
0x18002c53d  lea     rcx, [rbx+48h]; lpCriticalSection
0x18002c541  call    cs:__imp_DeleteCriticalSection
0x18002c548  nop     dword ptr [rax+rax+00h]
0x18002c54d  lea     rcx, [rbx+30h]
0x18002c551  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18002c556  lea     rcx, [rbx+20h]
0x18002c55a  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18002c55f  lea     rcx, [rbx+18h]
0x18002c563  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18002c568  lea     rcx, [rbx+10h]
0x18002c56c  call    ??1?$unique_any@U?$handle_traits@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,int (*)(void *),&WinHttpCloseHandle(void *),0>>::~unique_any<tlx::handle_traits<void *,int (*)(void *),&WinHttpCloseHandle(void *),0>>(void)
0x18002c571  lea     rcx, [rbx+8]
0x18002c575  call    ??1?$unique_any@U?$handle_traits@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,int (*)(void *),&WinHttpCloseHandle(void *),0>>::~unique_any<tlx::handle_traits<void *,int (*)(void *),&WinHttpCloseHandle(void *),0>>(void)
0x18002c57a  mov     rcx, rbx
0x18002c57d  add     rsp, 28h
0x18002c581  pop     r14
0x18002c583  pop     rdi
0x18002c584  pop     rsi
0x18002c585  pop     rbx
0x18002c586  jmp     ??1?$unique_any@U?$handle_traits@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,int (*)(void *),&WinHttpCloseHandle(void *),0>>::~unique_any<tlx::handle_traits<void *,int (*)(void *),&WinHttpCloseHandle(void *),0>>(void)
```
