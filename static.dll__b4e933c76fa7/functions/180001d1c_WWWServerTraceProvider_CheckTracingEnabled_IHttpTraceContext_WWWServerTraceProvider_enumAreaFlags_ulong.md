# WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)

- ea: `0x180001d1c`
- end: `0x180001d84`
- name: `?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z`
- size: `104`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002dd8`

## callees

- `0x180001d1c`
- `0x180007010`

## pseudocode

```c
_BOOL8 __fastcall WWWServerTraceProvider::CheckTracingEnabled(
        int (__fastcall ***a1)(_QWORD, GUID **),
        int a2,
        unsigned int a3)
{
  int (__fastcall **v4)(_QWORD, GUID **); // rax
  GUID *v7; // [rsp+20h] [rbp-28h] BYREF
  __int128 v8; // [rsp+28h] [rbp-20h]

  v7 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v4 = *a1;
  v8 = 0;
  return (*v4)(a1, &v7) >= 0 && DWORD2(v8) && DWORD1(v8) >= a3 && ((_DWORD)v8 == a2 || (a2 & (unsigned int)v8) == a2);
}

```

## disassembly

```asm
0x180001d1c  mov     [rsp+arg_0], rbx
0x180001d21  push    rdi
0x180001d22  sub     rsp, 40h
0x180001d26  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180001d2d  mov     ebx, edx
0x180001d2f  mov     [rsp+48h+var_28], rax
0x180001d34  lea     rdx, [rsp+48h+var_28]
0x180001d39  mov     rax, [rcx]
0x180001d3c  xorps   xmm0, xmm0
0x180001d3f  mov     edi, r8d
0x180001d42  movdqu  [rsp+48h+var_20], xmm0
0x180001d48  mov     rax, [rax]
0x180001d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d50  test    eax, eax
0x180001d52  js      short loc_180001D77
0x180001d54  cmp     dword ptr [rsp+48h+var_20+8], 0
0x180001d59  jz      short loc_180001D77
0x180001d5b  cmp     dword ptr [rsp+48h+var_20+4], edi
0x180001d5f  jb      short loc_180001D77
0x180001d61  mov     rax, qword ptr [rsp+48h+var_20]
0x180001d66  cmp     eax, ebx
0x180001d68  jz      short loc_180001D70
0x180001d6a  and     eax, ebx
0x180001d6c  cmp     eax, ebx
0x180001d6e  jnz     short loc_180001D77
0x180001d70  mov     eax, 1
0x180001d75  jmp     short loc_180001D79
0x180001d77  xor     eax, eax
0x180001d79  mov     rbx, [rsp+48h+arg_0]
0x180001d7e  add     rsp, 40h
0x180001d82  pop     rdi
0x180001d83  retn
```
