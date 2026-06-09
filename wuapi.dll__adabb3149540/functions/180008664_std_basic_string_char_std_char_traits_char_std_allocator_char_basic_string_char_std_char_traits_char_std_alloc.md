# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x180008664`
- end: `0x1800086d6`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `114`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000576c`
- `0x1800059b8`
- `0x180006518`
- `0x180006810`
- `0x180006874`
- `0x1800167ed`
- `0x1800167ff`
- `0x1800168cb`
- `0x1800168f7`
- `0x180016947`
- `0x180016b32`

## callees

- `0x180008664`
- `0x1800100d4`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800086cf`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800086cf`

## pseudocode

```c
void __fastcall std::string::~string(__int64 a1)
{
  unsigned __int64 v1; // rdx
  _QWORD *v3; // rcx
  const struct std::nothrow_t *v4; // rdx

  v1 = *(_QWORD *)(a1 + 24);
  if ( v1 > 0xF )
  {
    v3 = *(_QWORD **)a1;
    v4 = (const struct std::nothrow_t *)(v1 + 1);
    if ( (unsigned __int64)v4 >= 0x1000 )
    {
      v4 = (const struct std::nothrow_t *)((char *)v4 + 39);
      if ( (unsigned __int64)v3 - *(v3 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v3 = (_QWORD *)*(v3 - 1);
    }
    operator delete(v3, v4);
  }
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 15;
  *(_BYTE *)a1 = 0;
}

```

## disassembly

```asm
0x180008664  push    rbx
0x180008666  sub     rsp, 30h
0x18000866a  mov     rdx, [rcx+18h]
0x18000866e  mov     rbx, rcx
0x180008671  cmp     rdx, 0Fh
0x180008675  jbe     short loc_1800086A3
0x180008677  mov     rcx, [rcx]
0x18000867a  inc     rdx
0x18000867d  cmp     rdx, 1000h
0x180008684  jb      short loc_18000869E
0x180008686  mov     rax, [rcx-8]
0x18000868a  add     rdx, 27h ; '''; struct std::nothrow_t *
0x18000868e  sub     rcx, rax
0x180008691  sub     rcx, 8
0x180008695  cmp     rcx, 1Fh
0x180008699  ja      short loc_1800086BC
0x18000869b  mov     rcx, rax; void *
0x18000869e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800086a3  mov     qword ptr [rbx+10h], 0
0x1800086ab  mov     qword ptr [rbx+18h], 0Fh
0x1800086b3  mov     byte ptr [rbx], 0
0x1800086b6  add     rsp, 30h
0x1800086ba  pop     rbx
0x1800086bb  retn
0x1800086bc  xor     r9d, r9d; LineNo
0x1800086bf  mov     [rsp+38h+Reserved], 0; Reserved
0x1800086c8  xor     r8d, r8d; FileName
0x1800086cb  xor     edx, edx; FunctionName
0x1800086cd  xor     ecx, ecx; Expression
0x1800086cf  call    cs:__imp__invoke_watson
```
