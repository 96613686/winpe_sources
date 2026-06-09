# ParsedObjectPath::ParsedObjectPath(void)

- ea: `0x180014404`
- end: `0x1800144a8`
- name: `??0ParsedObjectPath@@QEAA@XZ`
- size: `164`
- prototype: `ParsedObjectPath *__fastcall(ParsedObjectPath *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800147e4`

## callees

- `0x180014404`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014427`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014476`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014427`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014476`

## pseudocode

```c
ParsedObjectPath *__fastcall ParsedObjectPath::ParsedObjectPath(ParsedObjectPath *this)
{
  void *v2; // rax
  __int64 i; // r8
  void *v4; // rax
  __int64 j; // rdx

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 3) = 2;
  v2 = CWin32DefaultArena::WbemMemAlloc(0x10u);
  *((_QWORD *)this + 2) = v2;
  if ( v2 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 3); i = (unsigned int)(i + 1) )
      *(_QWORD *)(*((_QWORD *)this + 2) + 8 * i) = 0;
  }
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_DWORD *)this + 9) = 2;
  v4 = CWin32DefaultArena::WbemMemAlloc(0x10u);
  *((_QWORD *)this + 5) = v4;
  if ( v4 )
  {
    for ( j = 0; (unsigned int)j < *((_DWORD *)this + 9); j = (unsigned int)(j + 1) )
      *(_QWORD *)(*((_QWORD *)this + 5) + 8 * j) = 0;
  }
  return this;
}

```

## disassembly

```asm
0x180014404  push    rbx
0x180014406  sub     rsp, 20h
0x18001440a  mov     rbx, rcx
0x18001440d  mov     qword ptr [rcx], 0
0x180014414  mov     dword ptr [rcx+8], 0
0x18001441b  mov     dword ptr [rcx+0Ch], 2
0x180014422  mov     ecx, 10h
0x180014427  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001442d  mov     [rbx+10h], rax
0x180014431  test    rax, rax
0x180014434  jz      short loc_180014454
0x180014436  xor     r8d, r8d
0x180014439  cmp     [rbx+0Ch], r8d
0x18001443d  jbe     short loc_180014454
0x18001443f  mov     rax, [rbx+10h]
0x180014443  mov     qword ptr [rax+r8*8], 0
0x18001444b  inc     r8d
0x18001444e  cmp     r8d, [rbx+0Ch]
0x180014452  jb      short loc_18001443F
0x180014454  mov     ecx, 10h
0x180014459  mov     qword ptr [rbx+18h], 0
0x180014461  mov     dword ptr [rbx+20h], 0
0x180014468  mov     dword ptr [rbx+30h], 0
0x18001446f  mov     dword ptr [rbx+24h], 2
0x180014476  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001447c  mov     [rbx+28h], rax
0x180014480  test    rax, rax
0x180014483  jz      short loc_18001449F
0x180014485  xor     edx, edx
0x180014487  cmp     [rbx+24h], edx
0x18001448a  jbe     short loc_18001449F
0x18001448c  mov     rax, [rbx+28h]
0x180014490  mov     qword ptr [rax+rdx*8], 0
0x180014498  inc     edx
0x18001449a  cmp     edx, [rbx+24h]
0x18001449d  jb      short loc_18001448C
0x18001449f  mov     rax, rbx
0x1800144a2  add     rsp, 20h
0x1800144a6  pop     rbx
0x1800144a7  retn
```
