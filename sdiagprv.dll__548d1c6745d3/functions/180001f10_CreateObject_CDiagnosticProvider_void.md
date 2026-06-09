# CreateObject<CDiagnosticProvider>(void)

- ea: `0x180001f10`
- end: `0x180001f62`
- name: `??$CreateObject@VCDiagnosticProvider@@@@YAPEAUIUnknown@@XZ`
- size: `82`
- prototype: `CDiagnosticProvider *()`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001074`
- `0x180001f10`
- `0x18000650c`
- `0x180019010`

## pseudocode

```c
CDiagnosticProvider *CreateObject<CDiagnosticProvider>()
{
  CDiagnosticProvider *v0; // rax
  CDiagnosticProvider *v1; // rax
  CDiagnosticProvider *v2; // rbx

  v0 = (CDiagnosticProvider *)operator new(0xC8u);
  if ( !v0 )
    return 0;
  v1 = CDiagnosticProvider::CDiagnosticProvider(v0);
  v2 = v1;
  if ( v1 && (**((int (__fastcall ***)(__int64))v1 + 1))((__int64)v1 + 8) < 0 )
  {
    (*(void (__fastcall **)(CDiagnosticProvider *))(*(_QWORD *)v2 + 16LL))(v2);
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180001f10  push    rbx
0x180001f12  sub     rsp, 20h
0x180001f16  mov     ecx, 0C8h; Size
0x180001f1b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001f20  test    rax, rax
0x180001f23  jz      short loc_180001F57
0x180001f25  mov     rcx, rax; this
0x180001f28  call    ??0CDiagnosticProvider@@QEAA@XZ; CDiagnosticProvider::CDiagnosticProvider(void)
0x180001f2d  mov     rbx, rax
0x180001f30  test    rax, rax
0x180001f33  jz      short loc_180001F59
0x180001f35  lea     rcx, [rax+8]
0x180001f39  mov     rax, [rcx]
0x180001f3c  mov     rax, [rax]
0x180001f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f44  test    eax, eax
0x180001f46  jns     short loc_180001F59
0x180001f48  mov     rax, [rbx]
0x180001f4b  mov     rcx, rbx
0x180001f4e  mov     rax, [rax+10h]
0x180001f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f57  xor     ebx, ebx
0x180001f59  mov     rax, rbx
0x180001f5c  add     rsp, 20h
0x180001f60  pop     rbx
0x180001f61  retn
```
