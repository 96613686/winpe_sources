# RecursiveRemoveDirectory(ushort const *)

- ea: `0x180007770`
- end: `0x180007835`
- name: `?RecursiveRemoveDirectory@@YAJPEBG@Z`
- size: `197`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006f54`

## callees

- `0x180007770`
- `0x18000783c`
- `0x18000a010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x18000778d`
- `SHELL32!SHCreateItemFromParsingName` at `0x18000778d`

## pseudocode

```c
__int64 __fastcall RecursiveRemoveDirectory(const unsigned __int16 *a1)
{
  HWND v1; // rcx
  HRESULT v2; // ebx
  const struct _GUID *v3; // r8
  void *v4; // rcx
  void *v5; // rcx
  void *v7; // [rsp+38h] [rbp+10h] BYREF
  void *ppv; // [rsp+40h] [rbp+18h] BYREF

  ppv = 0;
  v2 = SHCreateItemFromParsingName(a1, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  if ( v2 >= 0 )
  {
    v7 = 0;
    v2 = SHCreateFileOperation(v1, 0x414u, v3, &v7);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(void *, void *, _QWORD))(*(_QWORD *)v7 + 144LL))(v7, ppv, 0);
      if ( v2 >= 0 )
        v2 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v7 + 168LL))(v7);
    }
    v4 = v7;
    if ( v7 )
    {
      v7 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  v5 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180007770  push    rbx
0x180007772  sub     rsp, 20h
0x180007776  lea     r9, [rsp+28h+ppv]; ppv
0x18000777b  mov     [rsp+28h+ppv], 0
0x180007784  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18000778b  xor     edx, edx; pbc
0x18000778d  call    cs:__imp_SHCreateItemFromParsingName
0x180007793  mov     ebx, eax
0x180007795  test    eax, eax
0x180007797  js      short loc_18000780E
0x180007799  lea     r9, [rsp+28h+arg_8]; void **
0x18000779e  mov     [rsp+28h+arg_8], 0
0x1800077a7  mov     edx, 414h; unsigned int
0x1800077ac  call    ?SHCreateFileOperation@@YAJPEAUHWND__@@KAEBU_GUID@@PEAPEAX@Z; SHCreateFileOperation(HWND__ *,ulong,_GUID const &,void * *)
0x1800077b1  mov     ebx, eax
0x1800077b3  test    eax, eax
0x1800077b5  js      short loc_1800077EF
0x1800077b7  mov     rcx, [rsp+28h+arg_8]
0x1800077bc  xor     r8d, r8d
0x1800077bf  mov     rdx, [rsp+28h+ppv]
0x1800077c4  mov     rax, [rcx]
0x1800077c7  mov     rax, [rax+90h]
0x1800077ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077d3  mov     ebx, eax
0x1800077d5  test    eax, eax
0x1800077d7  js      short loc_1800077EF
0x1800077d9  mov     rcx, [rsp+28h+arg_8]
0x1800077de  mov     rax, [rcx]
0x1800077e1  mov     rax, [rax+0A8h]
0x1800077e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077ed  mov     ebx, eax
0x1800077ef  mov     rcx, [rsp+28h+arg_8]
0x1800077f4  test    rcx, rcx
0x1800077f7  jz      short loc_18000780E
0x1800077f9  mov     [rsp+28h+arg_8], 0
0x180007802  mov     rax, [rcx]
0x180007805  mov     rax, [rax+10h]
0x180007809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000780e  mov     rcx, [rsp+28h+ppv]
0x180007813  test    rcx, rcx
0x180007816  jz      short loc_18000782D
0x180007818  mov     [rsp+28h+ppv], 0
0x180007821  mov     rax, [rcx]
0x180007824  mov     rax, [rax+10h]
0x180007828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000782d  mov     eax, ebx
0x18000782f  add     rsp, 20h
0x180007833  pop     rbx
0x180007834  retn
```
