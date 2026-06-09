# InitializeUSCloserThreadpool(void)

- ea: `0x1800243ac`
- end: `0x1800244be`
- name: `?InitializeUSCloserThreadpool@@YAJXZ`
- size: `274`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180024220`
- `0x1800701e0`

## callees

- `0x1800068f0`
- `0x1800243ac`
- `0x1800ab230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800243b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800243b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800244b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800244b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002445d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002445d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002448f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002448f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002443c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002443c`

## string_xrefs

- `0x180024478`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\clientobjects.cpp`

## pseudocode

```c
__int64 InitializeUSCloserThreadpool(void)
{
  PTP_POOL Threadpool; // rax
  signed int LastError; // eax
  unsigned int v2; // ebx

  EnterCriticalSection(&CriticalSection);
  if ( qword_18010E060 )
    goto LABEL_7;
  g_USCloserTPEnv.Version = 3;
  xmmword_18010C200 = 0;
  pcbe = &g_USCloserTPEnv;
  qword_18010C1E8 = 0;
  qword_18010C1F0 = 0;
  qword_18010C1F8 = 0;
  qword_18010C210 = 0;
  dword_18010C218 = 0;
  dword_18010C21C = 1;
  dword_18010C220 = 72;
  Threadpool = CreateThreadpool(0);
  tlx::auto_xxx<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),0>::reset(
    &qword_18010E060,
    Threadpool);
  if ( qword_18010E060 )
  {
    SetThreadpoolThreadMaximum(qword_18010E060, 5u);
    pcbe->Pool = qword_18010E060;
LABEL_7:
    v2 = 0;
    goto LABEL_8;
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  Log_UnistoreHREvent_0(
    v2,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\clientobjects.cpp",
    222);
LABEL_8:
  LeaveCriticalSection(&CriticalSection);
  return v2;
}

```

## disassembly

```asm
0x1800243ac  push    rbx
0x1800243ae  sub     rsp, 30h
0x1800243b2  lea     rcx, CriticalSection; lpCriticalSection
0x1800243b9  call    cs:__imp_EnterCriticalSection
0x1800243bf  cmp     cs:qword_18010E060, 0
0x1800243c7  jnz     loc_1800244A7
0x1800243cd  xorps   xmm0, xmm0
0x1800243d0  mov     cs:?g_USCloserTPEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A, 3; _TP_CALLBACK_ENVIRON_V3 g_USCloserTPEnv
0x1800243da  lea     rax, ?g_USCloserTPEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; _TP_CALLBACK_ENVIRON_V3 g_USCloserTPEnv
0x1800243e1  movdqa  cs:xmmword_18010C200, xmm0
0x1800243e9  xor     ecx, ecx; reserved
0x1800243eb  mov     cs:pcbe, rax
0x1800243f2  mov     cs:qword_18010C1E8, 0
0x1800243fd  mov     cs:qword_18010C1F0, 0
0x180024408  mov     cs:qword_18010C1F8, 0
0x180024413  mov     cs:qword_18010C210, 0
0x18002441e  mov     cs:dword_18010C218, 0
0x180024428  mov     cs:dword_18010C21C, 1
0x180024432  mov     cs:dword_18010C220, 48h ; 'H'
0x18002443c  call    cs:__imp_CreateThreadpool
0x180024442  mov     rdx, rax
0x180024445  lea     rcx, qword_18010E060
0x18002444c  call    ?reset@?$auto_xxx@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@Z$0A@@tlx@@QEAAXPEAU_TP_POOL@@@Z; tlx::auto_xxx<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),0>::reset(_TP_POOL *)
0x180024451  mov     rcx, cs:qword_18010E060; ptpp
0x180024458  test    rcx, rcx
0x18002445b  jnz     short loc_18002448A
0x18002445d  call    cs:__imp_GetLastError
0x180024463  mov     ebx, eax
0x180024465  test    eax, eax
0x180024467  jle     short loc_180024472
0x180024469  movzx   ebx, ax
0x18002446c  or      ebx, 80070000h
0x180024472  mov     r9d, 0DEh
0x180024478  lea     r8, aOnecoreuapBase_59; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002447f  xor     edx, edx
0x180024481  mov     ecx, ebx
0x180024483  call    Log_UnistoreHREvent_0
0x180024488  jmp     short loc_1800244A9
0x18002448a  mov     edx, 5; cthrdMost
0x18002448f  call    cs:__imp_SetThreadpoolThreadMaximum
0x180024495  mov     rax, cs:pcbe
0x18002449c  mov     rdx, cs:qword_18010E060
0x1800244a3  mov     [rax+8], rdx
0x1800244a7  xor     ebx, ebx
0x1800244a9  lea     rcx, CriticalSection; lpCriticalSection
0x1800244b0  call    cs:__imp_LeaveCriticalSection
0x1800244b6  mov     eax, ebx
0x1800244b8  add     rsp, 30h
0x1800244bc  pop     rbx
0x1800244bd  retn
```
