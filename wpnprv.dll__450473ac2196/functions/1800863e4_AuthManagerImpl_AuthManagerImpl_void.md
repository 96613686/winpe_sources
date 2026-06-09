# AuthManagerImpl::~AuthManagerImpl(void)

- ea: `0x1800863e4`
- end: `0x1800864b4`
- name: `??1AuthManagerImpl@@UEAA@XZ`
- size: `208`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800864c0`

## callees

- `0x18000fe2c`
- `0x1800863e4`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008646c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008646c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008643d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008643d`

## pseudocode

```c
void __fastcall AuthManagerImpl::~AuthManagerImpl(struct _RTL_CRITICAL_SECTION *this)
{
  char *SpinCount; // rcx
  HANDLE LockSemaphore; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&AuthManagerImpl::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids);
  }
  SpinCount = (char *)this->SpinCount;
  if ( (unsigned __int64)(SpinCount - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(SpinCount);
    this->SpinCount = 0;
  }
  LockSemaphore = this->LockSemaphore;
  if ( LockSemaphore )
  {
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)LockSemaphore + 16LL))(LockSemaphore);
    this->LockSemaphore = 0;
  }
  DeleteCriticalSection(this + 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids);
  }
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&IAuthManager::`vftable';
}

```

## disassembly

```asm
0x1800863e4  mov     [rsp+arg_0], rbx
0x1800863e9  push    rdi
0x1800863ea  sub     rsp, 20h
0x1800863ee  mov     rbx, rcx
0x1800863f1  lea     rax, ??_7AuthManagerImpl@@6B@; const AuthManagerImpl::`vftable'
0x1800863f8  mov     [rcx], rax
0x1800863fb  lea     rdi, WPP_GLOBAL_Control
0x180086402  mov     rcx, cs:WPP_GLOBAL_Control
0x180086409  cmp     rcx, rdi
0x18008640c  jz      short loc_18008642F
0x18008640e  test    byte ptr [rcx+1Ch], 10h
0x180086412  jz      short loc_18008642F
0x180086414  cmp     byte ptr [rcx+19h], 6
0x180086418  jb      short loc_18008642F
0x18008641a  mov     edx, 0Ch
0x18008641f  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x180086426  mov     rcx, [rcx+10h]
0x18008642a  call    WPP_SF_
0x18008642f  mov     rcx, [rbx+20h]; hObject
0x180086433  lea     rax, [rcx-1]
0x180086437  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008643b  ja      short loc_18008644B
0x18008643d  call    cs:__imp_CloseHandle
0x180086443  mov     qword ptr [rbx+20h], 0
0x18008644b  mov     rcx, [rbx+18h]
0x18008644f  test    rcx, rcx
0x180086452  jz      short loc_180086468
0x180086454  mov     rax, [rcx]
0x180086457  mov     rax, [rax+10h]
0x18008645b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086460  mov     qword ptr [rbx+18h], 0
0x180086468  lea     rcx, [rbx+28h]; lpCriticalSection
0x18008646c  call    cs:__imp_DeleteCriticalSection
0x180086472  mov     rcx, cs:WPP_GLOBAL_Control
0x180086479  cmp     rcx, rdi
0x18008647c  jz      short loc_18008649F
0x18008647e  test    byte ptr [rcx+1Ch], 10h
0x180086482  jz      short loc_18008649F
0x180086484  cmp     byte ptr [rcx+19h], 6
0x180086488  jb      short loc_18008649F
0x18008648a  mov     edx, 0Dh
0x18008648f  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x180086496  mov     rcx, [rcx+10h]
0x18008649a  call    WPP_SF_
0x18008649f  lea     rax, ??_7IAuthManager@@6B@; const IAuthManager::`vftable'
0x1800864a6  mov     [rbx], rax
0x1800864a9  mov     rbx, [rsp+28h+arg_0]
0x1800864ae  add     rsp, 20h
0x1800864b2  pop     rdi
0x1800864b3  retn
```
