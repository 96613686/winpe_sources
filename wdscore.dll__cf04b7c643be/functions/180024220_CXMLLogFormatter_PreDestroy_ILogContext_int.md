# CXMLLogFormatter::PreDestroy(ILogContext *,int)

- ea: `0x180024220`
- end: `0x18002428a`
- name: `?PreDestroy@CXMLLogFormatter@@UEAAXPEAVILogContext@@H@Z`
- size: `106`
- prototype: `void __fastcall(CXMLLogFormatter *__hidden this, struct ILogContext *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18001ac00`
- `0x180024220`
- `0x18002a010`

## string_xrefs

- `0x180024244`: `</rs:data>\n</xml>\n`

## pseudocode

```c
void __fastcall CXMLLogFormatter::PreDestroy(CXMLLogFormatter *this, struct ILogContext *a2, int a3)
{
  __int64 (__fastcall *v4)(struct ILogContext *, __int64); // rax
  char *v5; // rax
  __int64 v6; // r10
  __int64 v7; // rdx

  v4 = *(__int64 (__fastcall **)(struct ILogContext *, __int64))(*(_QWORD *)a2 + 8LL);
  if ( a3 )
  {
    v5 = (char *)v4(a2, 19);
    if ( (int)StringCchCopyA(v5, 0x13u, "</rs:data>\n</xml>\n") >= 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( *(_BYTE *)(v6 + v7) );
      (*(void (__fastcall **)(struct ILogContext *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(a2, v7, 0);
    }
  }
  else
  {
    ((void (__fastcall *)(struct ILogContext *, _QWORD, _QWORD))v4)(a2, 0, 0);
  }
}

```

## disassembly

```asm
0x180024220  push    rbx
0x180024222  sub     rsp, 20h
0x180024226  mov     rax, [rdx]
0x180024229  mov     rbx, rdx
0x18002422c  mov     rcx, rdx
0x18002422f  mov     rax, [rax+8]
0x180024233  test    r8d, r8d
0x180024236  jz      short loc_180024279
0x180024238  xor     r8d, r8d
0x18002423b  lea     edx, [r8+13h]
0x18002423f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024244  lea     r8, aRsDataXml; "</rs:data>\n</xml>\n"
0x18002424b  mov     edx, 13h; unsigned __int64
0x180024250  mov     rcx, rax; char *
0x180024253  mov     r10, rax
0x180024256  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18002425b  test    eax, eax
0x18002425d  js      short loc_180024283
0x18002425f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180024263  inc     rdx
0x180024266  cmp     byte ptr [r10+rdx], 0
0x18002426b  jnz     short loc_180024263
0x18002426d  mov     rax, [rbx]
0x180024270  mov     rcx, rbx
0x180024273  mov     rax, [rax+10h]
0x180024277  jmp     short loc_18002427B
0x180024279  xor     edx, edx
0x18002427b  xor     r8d, r8d
0x18002427e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024283  add     rsp, 20h
0x180024287  pop     rbx
0x180024288  retn
```
