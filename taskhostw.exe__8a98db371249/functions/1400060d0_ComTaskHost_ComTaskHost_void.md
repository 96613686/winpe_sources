# ComTaskHost::~ComTaskHost(void)

- ea: `0x1400060d0`
- end: `0x140006196`
- name: `??1ComTaskHost@@UEAA@XZ`
- size: `198`
- prototype: `void __fastcall(ComTaskHost *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140006090`

## callees

- `0x1400060d0`
- `0x1400061a0`
- `0x140009370`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006109`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006109`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000618d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000618d`

## pseudocode

```c
void __fastcall ComTaskHost::~ComTaskHost(ComTaskHost *this)
{
  char *v2; // rcx
  __int64 v3; // rcx
  _bstr_t::Data_t *v4; // rcx
  _bstr_t::Data_t *v5; // rcx

  *(_QWORD *)this = &ComTaskHost::`vftable'{for `ITaskHandlerStatus'};
  *((_QWORD *)this + 1) = &ComTaskHost::`vftable'{for `ITaskVariables'};
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids, this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v2 = (char *)_InterlockedExchange64((volatile __int64 *)this + 10, 0);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  v3 = _InterlockedExchange64((volatile __int64 *)this + 9, 0);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = (_bstr_t::Data_t *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    _bstr_t::Data_t::Release(v4);
    *((_QWORD *)this + 7) = 0;
  }
  v5 = (_bstr_t::Data_t *)*((_QWORD *)this + 5);
  if ( v5 )
  {
    _bstr_t::Data_t::Release(v5);
    *((_QWORD *)this + 5) = 0;
  }
}

```

## disassembly

```asm
0x1400060d0  mov     [rsp+arg_0], rbx
0x1400060d5  push    rdi
0x1400060d6  sub     rsp, 20h
0x1400060da  mov     rbx, rcx
0x1400060dd  lea     rax, ??_7ComTaskHost@@6BITaskHandlerStatus@@@; const ComTaskHost::`vftable'{for `ITaskHandlerStatus'}
0x1400060e4  mov     [rcx], rax
0x1400060e7  lea     rax, ??_7ComTaskHost@@6BITaskVariables@@@; const ComTaskHost::`vftable'{for `ITaskVariables'}
0x1400060ee  mov     [rcx+8], rax
0x1400060f2  lea     rax, WPP_GLOBAL_Control
0x1400060f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140006100  cmp     rcx, rax
0x140006103  jnz     short loc_14000616A
0x140006105  lea     rcx, [rbx+60h]; lpCriticalSection
0x140006109  call    cs:__imp_DeleteCriticalSection
0x14000610f  nop
0x140006110  xor     edi, edi
0x140006112  mov     ecx, edi
0x140006114  xchg    rcx, [rbx+50h]; hObject
0x140006118  lea     rax, [rcx-1]
0x14000611c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140006120  jbe     short loc_14000618D
0x140006122  mov     rcx, rdi
0x140006125  xchg    rcx, [rbx+48h]
0x140006129  test    rcx, rcx
0x14000612c  jz      short loc_14000613B
0x14000612e  mov     rax, [rcx]
0x140006131  mov     rax, [rax+10h]
0x140006135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000613a  nop
0x14000613b  mov     rcx, [rbx+38h]; this
0x14000613f  test    rcx, rcx
0x140006142  jz      short loc_14000614D
0x140006144  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x140006149  mov     [rbx+38h], rdi
0x14000614d  mov     rcx, [rbx+28h]; this
0x140006151  test    rcx, rcx
0x140006154  jz      short loc_14000615F
0x140006156  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x14000615b  mov     [rbx+28h], rdi
0x14000615f  mov     rbx, [rsp+28h+arg_0]
0x140006164  add     rsp, 20h
0x140006168  pop     rdi
0x140006169  retn
0x14000616a  test    byte ptr [rcx+1Ch], 4
0x14000616e  jz      short loc_140006105
0x140006170  mov     edx, 0Ah
0x140006175  mov     r9, rbx
0x140006178  lea     r8, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids
0x14000617f  mov     rcx, [rcx+10h]
0x140006183  call    WPP_SF_q
0x140006188  jmp     loc_140006105
0x14000618d  call    cs:__imp_CloseHandle
0x140006193  jmp     short loc_140006122
```
