# std::vector<std::filesystem::path,std::allocator<std::filesystem::path>>::~vector<std::filesystem::path,std::allocator<std::filesystem::path>>(void)

- ea: `0x1800185a8`
- end: `0x18001864e`
- name: `??1?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@QEAA@XZ`
- size: `166`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `38`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000f290`
- `0x180018654`
- `0x18001d39c`
- `0x18001dca0`
- `0x18002edd0`
- `0x18002f190`
- `0x18002f414`
- `0x180035a44`
- `0x180035b3c`
- `0x180038080`
- `0x180038ebc`
- `0x180038fe8`
- `0x180039e64`
- `0x18003a47c`
- `0x1800425d0`
- `0x180048370`
- `0x18004f7cc`
- `0x18004f974`
- `0x18004facc`
- `0x180050e54`
- `0x18005115c`
- `0x1800566c0`
- `0x180056ec4`
- `0x180057694`
- `0x180058c28`
- `0x18005a208`
- `0x18005c1a4`
- `0x18005e918`
- `0x18006045c`
- `0x180060508`
- `0x180069800`
- `0x180099e19`
- `0x180099e2b`
- `0x180099e3d`
- `0x18009a104`
- `0x18009a13a`
- `0x18009c191`
- `0x18009c372`

## callees

- `0x1800185a8`
- `0x180018eec`
- `0x18008ffd4`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180018647`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180018647`

## pseudocode

```c
void __fastcall std::vector<std::filesystem::path>::~vector<std::filesystem::path>(__int64 *a1)
{
  __int64 v1; // rbx
  __int64 v3; // rsi
  _QWORD *v4; // rcx
  unsigned __int64 v5; // rdx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = a1[1];
    while ( v1 != v3 )
    {
      std::wstring::~wstring(v1);
      v1 += 32;
    }
    v4 = (_QWORD *)*a1;
    v5 = (a1[2] - *a1) & 0xFFFFFFFFFFFFFFE0uLL;
    if ( v5 >= 0x1000 )
    {
      v5 += 39LL;
      if ( (unsigned __int64)v4 - *(v4 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v4 = (_QWORD *)*(v4 - 1);
    }
    operator delete(v4, v5);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x1800185a8  mov     [rsp+arg_8], rbx
0x1800185ad  mov     [rsp+arg_10], rsi
0x1800185b2  push    rdi
0x1800185b3  sub     rsp, 30h
0x1800185b7  mov     rbx, [rcx]
0x1800185ba  mov     rdi, rcx
0x1800185bd  test    rbx, rbx
0x1800185c0  jz      short loc_180018624
0x1800185c2  mov     rsi, [rcx+8]
0x1800185c6  jmp     short loc_1800185D4
0x1800185c8  mov     rcx, rbx
0x1800185cb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800185d0  add     rbx, 20h ; ' '
0x1800185d4  cmp     rbx, rsi
0x1800185d7  jnz     short loc_1800185C8
0x1800185d9  mov     rcx, [rdi]
0x1800185dc  mov     rdx, [rdi+10h]
0x1800185e0  sub     rdx, rcx
0x1800185e3  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800185e7  cmp     rdx, 1000h
0x1800185ee  jb      short loc_180018608
0x1800185f0  mov     rax, [rcx-8]
0x1800185f4  add     rdx, 27h ; '''; unsigned __int64
0x1800185f8  sub     rcx, rax
0x1800185fb  sub     rcx, 8
0x1800185ff  cmp     rcx, 1Fh
0x180018603  ja      short loc_180018634
0x180018605  mov     rcx, rax; void *
0x180018608  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001860d  mov     qword ptr [rdi], 0
0x180018614  mov     qword ptr [rdi+8], 0
0x18001861c  mov     qword ptr [rdi+10h], 0
0x180018624  mov     rbx, [rsp+38h+arg_8]
0x180018629  mov     rsi, [rsp+38h+arg_10]
0x18001862e  add     rsp, 30h
0x180018632  pop     rdi
0x180018633  retn
0x180018634  xor     r9d, r9d; LineNo
0x180018637  mov     [rsp+38h+Reserved], 0; Reserved
0x180018640  xor     r8d, r8d; FileName
0x180018643  xor     edx, edx; FunctionName
0x180018645  xor     ecx, ecx; Expression
0x180018647  call    cs:__imp__invoke_watson
```
