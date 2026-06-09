# COInetProt::~COInetProt(void)

- ea: `0x180035468`
- end: `0x180035645`
- name: `??1COInetProt@@QEAA@XZ`
- size: `477`
- prototype: `void __fastcall(COInetProt *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180034e88`

## callees

- `0x180035468`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035563`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180035563`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003560f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800354f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035538`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035550`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800354f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035538`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035550`
- `OLEAUT32!__imp_SysFreeString` at `0x180035629`
- `OLEAUT32!__imp_SysFreeString` at `0x180035629`

## pseudocode

```c
void __fastcall COInetProt::~COInetProt(COInetProt *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  __int64 v8; // rdi
  OLECHAR *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx

  *(_QWORD *)this = &COInetProt::`vftable'{for `IInternetProtocolEx'};
  *((_QWORD *)this + 1) = &COInetProt::`vftable'{for `IInternetProtocolSink'};
  *((_QWORD *)this + 2) = &COInetProt::`vftable'{for `IServiceProvider'};
  *((_QWORD *)this + 3) = &COInetProt::`vftable'{for `IInternetPriority'};
  *((_QWORD *)this + 4) = &COInetProt::`vftable'{for `IInternetPriorityInternal'};
  *((_QWORD *)this + 5) = &COInetProt::`vftable'{for `IUriContainer'};
  *((_QWORD *)this + 6) = &COInetProt::`vftable'{for `IBindingExInternal'};
  v2 = *((_QWORD *)this + 28);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 28) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 24);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)this + 25);
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)this + 26);
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = (void *)*((_QWORD *)this + 27);
  if ( v6 )
    CoTaskMemFree(v6);
  v7 = (void *)*((_QWORD *)this + 19);
  if ( v7 )
    CoTaskMemFree(v7);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  v8 = *((_QWORD *)this + 30);
  *((_QWORD *)this + 29) = &CUString::`vftable';
  if ( v8 || *((_DWORD *)this + 62) != 11 )
  {
    v9 = (OLECHAR *)*((_QWORD *)this + 32);
    if ( v9 )
    {
      SysFreeString(v9);
      *((_QWORD *)this + 32) = 0;
    }
    *((_QWORD *)this + 33) = 0;
    *((_DWORD *)this + 68) = 0;
    if ( v8 )
    {
      v10 = *((_QWORD *)this + 30);
      if ( v10 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        *((_QWORD *)this + 30) = 0;
      }
    }
  }
  *((_DWORD *)this + 62) = 11;
  v11 = *((_QWORD *)this + 15);
  if ( v11 )
  {
    *((_QWORD *)this + 15) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
}

```

## disassembly

```asm
0x180035468  mov     [rsp+arg_0], rbx
0x18003546d  push    rdi
0x18003546e  sub     rsp, 20h
0x180035472  lea     rax, ??_7COInetProt@@6BIInternetProtocolEx@@@; const COInetProt::`vftable'{for `IInternetProtocolEx'}
0x180035479  mov     rbx, rcx
0x18003547c  mov     [rcx], rax
0x18003547f  lea     rax, ??_7COInetProt@@6BIInternetProtocolSink@@@; const COInetProt::`vftable'{for `IInternetProtocolSink'}
0x180035486  mov     [rcx+8], rax
0x18003548a  lea     rax, ??_7COInetProt@@6BIServiceProvider@@@; const COInetProt::`vftable'{for `IServiceProvider'}
0x180035491  mov     [rcx+10h], rax
0x180035495  lea     rax, ??_7COInetProt@@6BIInternetPriority@@@; const COInetProt::`vftable'{for `IInternetPriority'}
0x18003549c  mov     [rcx+18h], rax
0x1800354a0  lea     rax, ??_7COInetProt@@6BIInternetPriorityInternal@@@; const COInetProt::`vftable'{for `IInternetPriorityInternal'}
0x1800354a7  mov     [rcx+20h], rax
0x1800354ab  lea     rax, ??_7COInetProt@@6BIUriContainer@@@; const COInetProt::`vftable'{for `IUriContainer'}
0x1800354b2  mov     [rcx+28h], rax
0x1800354b6  lea     rax, ??_7COInetProt@@6BIBindingExInternal@@@; const COInetProt::`vftable'{for `IBindingExInternal'}
0x1800354bd  mov     [rcx+30h], rax
0x1800354c1  mov     rcx, [rcx+0E0h]
0x1800354c8  test    rcx, rcx
0x1800354cb  jz      short loc_1800354E4
0x1800354cd  mov     rax, [rcx]
0x1800354d0  mov     rax, [rax+10h]
0x1800354d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800354d9  mov     qword ptr [rbx+0E0h], 0
0x1800354e4  mov     rcx, [rbx+0C0h]; pv
0x1800354eb  test    rcx, rcx
0x1800354ee  jz      short loc_1800354FC
0x1800354f0  call    cs:__imp_CoTaskMemFree
0x1800354f7  nop     dword ptr [rax+rax+00h]
0x1800354fc  mov     rcx, [rbx+0C8h]; pv
0x180035503  test    rcx, rcx
0x180035506  jz      short loc_180035514
0x180035508  call    cs:__imp_CoTaskMemFree
0x18003550f  nop     dword ptr [rax+rax+00h]
0x180035514  mov     rcx, [rbx+0D0h]; pv
0x18003551b  test    rcx, rcx
0x18003551e  jz      short loc_18003552C
0x180035520  call    cs:__imp_CoTaskMemFree
0x180035527  nop     dword ptr [rax+rax+00h]
0x18003552c  mov     rcx, [rbx+0D8h]; pv
0x180035533  test    rcx, rcx
0x180035536  jz      short loc_180035544
0x180035538  call    cs:__imp_CoTaskMemFree
0x18003553f  nop     dword ptr [rax+rax+00h]
0x180035544  mov     rcx, [rbx+98h]; pv
0x18003554b  test    rcx, rcx
0x18003554e  jz      short loc_18003555C
0x180035550  call    cs:__imp_CoTaskMemFree
0x180035557  nop     dword ptr [rax+rax+00h]
0x18003555c  lea     rcx, [rbx+128h]; lpCriticalSection
0x180035563  call    cs:__imp_DeleteCriticalSection
0x18003556a  nop     dword ptr [rax+rax+00h]
0x18003556f  mov     rdi, [rbx+0F0h]
0x180035576  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18003557d  mov     [rbx+0E8h], rax
0x180035584  test    rdi, rdi
0x180035587  jz      loc_18003561B
0x18003558d  mov     rcx, [rbx+100h]; bstrString
0x180035594  test    rcx, rcx
0x180035597  jnz     loc_180035629
0x18003559d  mov     qword ptr [rbx+108h], 0
0x1800355a8  mov     dword ptr [rbx+110h], 0
0x1800355b2  test    rdi, rdi
0x1800355b5  jz      short loc_1800355DA
0x1800355b7  mov     rcx, [rbx+0F0h]
0x1800355be  test    rcx, rcx
0x1800355c1  jz      short loc_1800355DA
0x1800355c3  mov     rax, [rcx]
0x1800355c6  mov     rax, [rax+10h]
0x1800355ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355cf  mov     qword ptr [rbx+0F0h], 0
0x1800355da  mov     dword ptr [rbx+0F8h], 0Bh
0x1800355e4  mov     rcx, [rbx+78h]
0x1800355e8  test    rcx, rcx
0x1800355eb  jz      short loc_180035601
0x1800355ed  mov     qword ptr [rbx+78h], 0
0x1800355f5  mov     rax, [rcx]
0x1800355f8  mov     rax, [rax+10h]
0x1800355fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035601  lea     rcx, [rbx+40h]
0x180035605  mov     rbx, [rsp+28h+arg_0]
0x18003560a  add     rsp, 20h
0x18003560e  pop     rdi
0x18003560f  jmp     cs:__imp_DeleteCriticalSection
0x18003561b  cmp     dword ptr [rbx+0F8h], 0Bh
0x180035622  jz      short loc_1800355DA
0x180035624  jmp     loc_18003558D
0x180035629  call    cs:__imp_SysFreeString
0x180035630  nop     dword ptr [rax+rax+00h]
0x180035635  mov     qword ptr [rbx+100h], 0
0x180035640  jmp     loc_18003559D
```
