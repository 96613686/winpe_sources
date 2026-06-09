# ParsedObjectPath::~ParsedObjectPath(void)

- ea: `0x1800144e8`
- end: `0x180014581`
- name: `??1ParsedObjectPath@@QEAA@XZ`
- size: `153`
- prototype: `void __fastcall(ParsedObjectPath *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800145b0`

## callees

- `0x1800144e8`
- `0x180014588`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800144fd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001451e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001452f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001453e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001456f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800144fd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001451e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001452f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001453e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001456f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ParsedObjectPath::~ParsedObjectPath(ParsedObjectPath *this, unsigned int a2)
{
  void *v3; // rcx
  __int64 i; // rdi
  void *v5; // rcx
  void *v6; // rcx
  __int64 j; // rdi
  KeyRef *v8; // rcx

  v3 = *(void **)this;
  if ( v3 )
    CWin32DefaultArena::WbemMemFree(v3);
  if ( *((_QWORD *)this + 2) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
    {
      v5 = *(void **)(*((_QWORD *)this + 2) + 8 * i);
      if ( v5 )
        CWin32DefaultArena::WbemMemFree(v5);
    }
    CWin32DefaultArena::WbemMemFree(*((void **)this + 2));
  }
  v6 = (void *)*((_QWORD *)this + 3);
  if ( v6 )
    CWin32DefaultArena::WbemMemFree(v6);
  if ( *((_QWORD *)this + 5) )
  {
    for ( j = 0; (unsigned int)j < *((_DWORD *)this + 8); j = (unsigned int)(j + 1) )
    {
      v8 = *(KeyRef **)(*((_QWORD *)this + 5) + 8 * j);
      if ( v8 )
        KeyRef::`scalar deleting destructor'(v8, a2);
    }
    CWin32DefaultArena::WbemMemFree(*((void **)this + 5));
  }
}

```

## disassembly

```asm
0x1800144e8  mov     [rsp+arg_0], rbx
0x1800144ed  push    rdi
0x1800144ee  sub     rsp, 20h
0x1800144f2  mov     rbx, rcx
0x1800144f5  mov     rcx, [rcx]
0x1800144f8  test    rcx, rcx
0x1800144fb  jz      short loc_180014503
0x1800144fd  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180014503  cmp     qword ptr [rbx+10h], 0
0x180014508  jz      short loc_180014535
0x18001450a  xor     edi, edi
0x18001450c  cmp     [rbx+8], edi
0x18001450f  jbe     short loc_18001452B
0x180014511  mov     rax, [rbx+10h]
0x180014515  mov     rcx, [rax+rdi*8]
0x180014519  test    rcx, rcx
0x18001451c  jz      short loc_180014524
0x18001451e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180014524  inc     edi
0x180014526  cmp     edi, [rbx+8]
0x180014529  jb      short loc_180014511
0x18001452b  mov     rcx, [rbx+10h]
0x18001452f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180014535  mov     rcx, [rbx+18h]
0x180014539  test    rcx, rcx
0x18001453c  jz      short loc_180014544
0x18001453e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180014544  cmp     qword ptr [rbx+28h], 0
0x180014549  jz      short loc_180014576
0x18001454b  xor     edi, edi
0x18001454d  cmp     [rbx+20h], edi
0x180014550  jbe     short loc_18001456B
0x180014552  mov     rax, [rbx+28h]
0x180014556  mov     rcx, [rax+rdi*8]; this
0x18001455a  test    rcx, rcx
0x18001455d  jz      short loc_180014564
0x18001455f  call    ??_GKeyRef@@QEAAPEAXI@Z; KeyRef::`scalar deleting destructor'(uint)
0x180014564  inc     edi
0x180014566  cmp     edi, [rbx+20h]
0x180014569  jb      short loc_180014552
0x18001456b  mov     rcx, [rbx+28h]
0x18001456f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180014575  nop
0x180014576  mov     rbx, [rsp+28h+arg_0]
0x18001457b  add     rsp, 20h
0x18001457f  pop     rdi
0x180014580  retn
```
