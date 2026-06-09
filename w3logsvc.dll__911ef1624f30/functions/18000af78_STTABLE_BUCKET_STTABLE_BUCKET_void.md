# STTABLE_BUCKET::~STTABLE_BUCKET(void)

- ea: `0x18000af78`
- end: `0x18000b005`
- name: `??1STTABLE_BUCKET@@UEAA@XZ`
- size: `141`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b100`

## callees

- `0x18000af78`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000afea`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000afea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aff4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aff4`

## pseudocode

```c
void __fastcall STTABLE_BUCKET::~STTABLE_BUCKET(struct _RTL_CRITICAL_SECTION *this)
{
  LONG *p_LockCount; // rdi
  volatile signed __int32 *v3; // rax
  _QWORD *v4; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&STTABLE_BUCKET::`vftable';
  p_LockCount = &this->LockCount;
  while ( 1 )
  {
    v3 = *(volatile signed __int32 **)p_LockCount;
    if ( *(LONG **)p_LockCount == p_LockCount )
      break;
    if ( *((LONG **)v3 + 1) != p_LockCount
      || (v4 = *(_QWORD **)v3, *(volatile signed __int32 **)(*(_QWORD *)v3 + 8LL) != v3) )
    {
      __fastfail(3u);
    }
    *(_QWORD *)p_LockCount = v4;
    v4[1] = p_LockCount;
    if ( _InterlockedExchangeAdd(v3 + 4, 0xFFFFFFFF) == 1 && v3 != (volatile signed __int32 *)8 )
      (**((void (__fastcall ***)(_QWORD *, __int64))v3 - 1))((_QWORD *)v3 - 1, 1);
  }
  if ( LODWORD(this->LockSemaphore) )
  {
    DeleteCriticalSection(this + 1);
    CloseHandle(this[2].DebugInfo);
  }
}

```

## disassembly

```asm
0x18000af78  mov     [rsp+arg_8], rbx
0x18000af7d  push    rdi
0x18000af7e  sub     rsp, 20h
0x18000af82  lea     rax, ??_7STTABLE_BUCKET@@6B@; const STTABLE_BUCKET::`vftable'
0x18000af89  mov     rbx, rcx
0x18000af8c  mov     [rcx], rax
0x18000af8f  lea     rdi, [rcx+8]
0x18000af93  mov     rax, [rdi]
0x18000af96  cmp     rax, rdi
0x18000af99  jz      short loc_18000AFE0
0x18000af9b  cmp     [rax+8], rdi
0x18000af9f  jnz     short loc_18000AFD9
0x18000afa1  mov     rcx, [rax]
0x18000afa4  cmp     [rcx+8], rax
0x18000afa8  jnz     short loc_18000AFD9
0x18000afaa  mov     [rdi], rcx
0x18000afad  mov     [rcx+8], rdi
0x18000afb1  lea     rcx, [rax-8]
0x18000afb5  or      eax, 0FFFFFFFFh
0x18000afb8  lock xadd [rcx+18h], eax
0x18000afbd  cmp     eax, 1
0x18000afc0  jnz     short loc_18000AF93
0x18000afc2  test    rcx, rcx
0x18000afc5  jz      short loc_18000AF93
0x18000afc7  mov     rax, [rcx]
0x18000afca  mov     edx, 1
0x18000afcf  mov     rax, [rax]
0x18000afd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afd7  jmp     short loc_18000AF93
0x18000afd9  mov     ecx, 3
0x18000afde  int     29h; Win8: RtlFailFast(ecx)
0x18000afe0  cmp     dword ptr [rbx+18h], 0
0x18000afe4  jz      short loc_18000AFFA
0x18000afe6  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000afea  call    cs:__imp_DeleteCriticalSection
0x18000aff0  mov     rcx, [rbx+50h]; hObject
0x18000aff4  call    cs:__imp_CloseHandle
0x18000affa  mov     rbx, [rsp+28h+arg_8]
0x18000afff  add     rsp, 20h
0x18000b003  pop     rdi
0x18000b004  retn
```
