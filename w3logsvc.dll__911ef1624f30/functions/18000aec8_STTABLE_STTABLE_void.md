# STTABLE::~STTABLE(void)

- ea: `0x18000aec8`
- end: `0x18000af6f`
- name: `??1STTABLE@@UEAA@XZ`
- size: `167`
- prototype: `void __fastcall(STTABLE *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000adac`
- `0x18000b0c0`
- `0x18000f14c`

## callees

- `0x18000aec8`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000af1c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000af1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000af47`

## pseudocode

```c
void __fastcall STTABLE::~STTABLE(STTABLE *this)
{
  __int64 v1; // rsi
  __int64 v2; // rdi
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  char *v5; // rcx

  v1 = *((_QWORD *)this + 2);
  v2 = 0;
  for ( *(_QWORD *)this = &STTABLE::`vftable'; (unsigned int)v2 < *((_DWORD *)this + 26); v2 = (unsigned int)(v2 + 1) )
  {
    v4 = *(void (__fastcall ****)(_QWORD, __int64))(v1 + 8 * v2);
    if ( v4 )
      (**v4)(v4, 1);
  }
  if ( *((_DWORD *)this + 28) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
    CloseHandle(*((HANDLE *)this + 21));
  }
  v5 = (char *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 1) = &STBUFF::`vftable';
  if ( v5 != (char *)this + 36 )
  {
    LocalFree(v5);
    *((_QWORD *)this + 2) = (char *)this + 36;
    *((_DWORD *)this + 7) = 64;
  }
  *((_DWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x18000aec8  mov     [rsp+arg_0], rbx
0x18000aecd  mov     [rsp+arg_8], rsi
0x18000aed2  push    rdi
0x18000aed3  sub     rsp, 20h
0x18000aed7  mov     rsi, [rcx+10h]
0x18000aedb  lea     rax, ??_7STTABLE@@6B@; const STTABLE::`vftable'
0x18000aee2  xor     edi, edi
0x18000aee4  mov     [rcx], rax
0x18000aee7  mov     rbx, rcx
0x18000aeea  cmp     [rcx+68h], edi
0x18000aeed  jbe     short loc_18000AF0F
0x18000aeef  mov     rcx, [rsi+rdi*8]
0x18000aef3  test    rcx, rcx
0x18000aef6  jz      short loc_18000AF08
0x18000aef8  mov     rax, [rcx]
0x18000aefb  mov     edx, 1
0x18000af00  mov     rax, [rax]
0x18000af03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af08  inc     edi
0x18000af0a  cmp     edi, [rbx+68h]
0x18000af0d  jb      short loc_18000AEEF
0x18000af0f  cmp     dword ptr [rbx+70h], 0
0x18000af13  jz      short loc_18000AF2F
0x18000af15  lea     rcx, [rbx+80h]; lpCriticalSection
0x18000af1c  call    cs:__imp_DeleteCriticalSection
0x18000af22  mov     rcx, [rbx+0A8h]; hObject
0x18000af29  call    cs:__imp_CloseHandle
0x18000af2f  mov     rcx, [rbx+10h]; hMem
0x18000af33  lea     rdi, [rbx+24h]
0x18000af37  lea     rax, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x18000af3e  mov     [rbx+8], rax
0x18000af42  cmp     rcx, rdi
0x18000af45  jz      short loc_18000AF58
0x18000af47  call    cs:__imp_LocalFree
0x18000af4d  mov     [rbx+10h], rdi
0x18000af51  mov     dword ptr [rbx+1Ch], 40h ; '@'
0x18000af58  mov     rsi, [rsp+28h+arg_8]
0x18000af5d  mov     dword ptr [rbx+18h], 0
0x18000af64  mov     rbx, [rsp+28h+arg_0]
0x18000af69  add     rsp, 20h
0x18000af6d  pop     rdi
0x18000af6e  retn
```
