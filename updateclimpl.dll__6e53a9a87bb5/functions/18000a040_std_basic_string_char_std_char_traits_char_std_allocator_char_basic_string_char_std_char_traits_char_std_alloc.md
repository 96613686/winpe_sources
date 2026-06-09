# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x18000a040`
- end: `0x18000a0b2`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `114`
- prototype: `void __fastcall(__int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009c54`
- `0x180009e50`
- `0x18000e660`
- `0x180015d15`
- `0x180015d27`
- `0x180015d39`
- `0x180015e2d`

## callees

- `0x18000a040`
- `0x180010334`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000a0ab`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000a0ab`

## pseudocode

```c
void __fastcall std::string::~string(__int64 a1)
{
  unsigned __int64 v1; // rdx
  _QWORD *v3; // rcx
  unsigned __int64 v4; // rdx

  v1 = *(_QWORD *)(a1 + 24);
  if ( v1 > 0xF )
  {
    v3 = *(_QWORD **)a1;
    v4 = v1 + 1;
    if ( v4 >= 0x1000 )
    {
      v4 += 39LL;
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
0x18000a040  push    rbx
0x18000a042  sub     rsp, 30h
0x18000a046  mov     rdx, [rcx+18h]
0x18000a04a  mov     rbx, rcx
0x18000a04d  cmp     rdx, 0Fh
0x18000a051  jbe     short loc_18000A07F
0x18000a053  mov     rcx, [rcx]
0x18000a056  inc     rdx
0x18000a059  cmp     rdx, 1000h
0x18000a060  jb      short loc_18000A07A
0x18000a062  mov     rax, [rcx-8]
0x18000a066  add     rdx, 27h ; '''; unsigned __int64
0x18000a06a  sub     rcx, rax
0x18000a06d  sub     rcx, 8
0x18000a071  cmp     rcx, 1Fh
0x18000a075  ja      short loc_18000A098
0x18000a077  mov     rcx, rax; void *
0x18000a07a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a07f  mov     qword ptr [rbx+10h], 0
0x18000a087  mov     qword ptr [rbx+18h], 0Fh
0x18000a08f  mov     byte ptr [rbx], 0
0x18000a092  add     rsp, 30h
0x18000a096  pop     rbx
0x18000a097  retn
0x18000a098  xor     r9d, r9d; LineNo
0x18000a09b  mov     [rsp+38h+Reserved], 0; Reserved
0x18000a0a4  xor     r8d, r8d; FileName
0x18000a0a7  xor     edx, edx; FunctionName
0x18000a0a9  xor     ecx, ecx; Expression
0x18000a0ab  call    cs:__imp__invoke_watson
```
