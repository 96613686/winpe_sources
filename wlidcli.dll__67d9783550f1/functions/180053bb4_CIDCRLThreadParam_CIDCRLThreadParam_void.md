# CIDCRLThreadParam::~CIDCRLThreadParam(void)

- ea: `0x180053bb4`
- end: `0x180053c0c`
- name: `??1CIDCRLThreadParam@@QEAA@XZ`
- size: `88`
- prototype: `void __fastcall(CIDCRLThreadParam *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180053c60`

## callees

- `0x180002d84`
- `0x180053bb4`
- `0x180053c90`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180053bee`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180053bee`

## pseudocode

```c
void __fastcall CIDCRLThreadParam::~CIDCRLThreadParam(CIDCRLThreadParam *this)
{
  void (__fastcall ***v2)(_QWORD); // rcx

  if ( *((_DWORD *)this + 12) )
  {
    v2 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 5);
    if ( v2 )
    {
      (**v2)(v2);
      operator delete(*((void **)this + 5));
      *((_QWORD *)this + 5) = 0;
    }
    else
    {
      SetThreadToken(0, 0);
    }
  }
  *((_QWORD *)this + 2) = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((CIDCRLThreadParam *)((char *)this + 16));
}

```

## disassembly

```asm
0x180053bb4  push    rbx
0x180053bb6  sub     rsp, 20h
0x180053bba  cmp     dword ptr [rcx+30h], 0
0x180053bbe  mov     rbx, rcx
0x180053bc1  jz      short loc_180053BF4
0x180053bc3  mov     rcx, [rcx+28h]
0x180053bc7  test    rcx, rcx
0x180053bca  jz      short loc_180053BEA
0x180053bcc  mov     rax, [rcx]
0x180053bcf  mov     rax, [rax]
0x180053bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053bd7  mov     rcx, [rbx+28h]; Block
0x180053bdb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180053be0  mov     qword ptr [rbx+28h], 0
0x180053be8  jmp     short loc_180053BF4
0x180053bea  xor     edx, edx; Token
0x180053bec  xor     ecx, ecx; Thread
0x180053bee  call    cs:__imp_SetThreadToken
0x180053bf4  lea     rcx, [rbx+10h]; this
0x180053bf8  lea     rax, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x180053bff  mov     [rcx], rax
0x180053c02  add     rsp, 20h
0x180053c06  pop     rbx
0x180053c07  jmp     ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
```
