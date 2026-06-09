# NSecurityLibrary::TUserContext::~TUserContext(void)

- ea: `0x1400146d4`
- end: `0x14001471a`
- name: `??1TUserContext@NSecurityLibrary@@UEAA@XZ`
- size: `70`
- prototype: `void __fastcall(NSecurityLibrary::TUserContext *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140012a20`
- `0x140014720`

## callees

- `0x1400146d4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400146f0`
- `KERNEL32!CloseHandle` at `0x1400146f0`

## pseudocode

```c
void __fastcall NSecurityLibrary::TUserContext::~TUserContext(NSecurityLibrary::TUserContext *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &NSecurityLibrary::TUserContext::`vftable';
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
    CloseHandle(v2);
  *((_DWORD *)this + 6) = -2147467259;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)((char *)this + 28) = 0;
  *((_DWORD *)this + 9) = 0;
}

```

## disassembly

```asm
0x1400146d4  push    rbx
0x1400146d6  sub     rsp, 20h
0x1400146da  lea     rax, ??_7TUserContext@NSecurityLibrary@@6B@; const NSecurityLibrary::TUserContext::`vftable'
0x1400146e1  mov     rbx, rcx
0x1400146e4  mov     [rcx], rax
0x1400146e7  mov     rcx, [rcx+10h]; hObject
0x1400146eb  test    rcx, rcx
0x1400146ee  jz      short loc_1400146F6
0x1400146f0  call    cs:__imp_CloseHandle
0x1400146f6  mov     dword ptr [rbx+18h], 80004005h
0x1400146fd  mov     qword ptr [rbx+10h], 0
0x140014705  mov     qword ptr [rbx+1Ch], 0
0x14001470d  mov     dword ptr [rbx+24h], 0
0x140014714  add     rsp, 20h
0x140014718  pop     rbx
0x140014719  retn
```
