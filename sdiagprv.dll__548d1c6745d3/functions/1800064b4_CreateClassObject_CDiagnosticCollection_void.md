# CreateClassObject<CDiagnosticCollection>(void)

- ea: `0x1800064b4`
- end: `0x180006506`
- name: `??$CreateClassObject@VCDiagnosticCollection@@@@YAPEAVCDiagnosticCollection@@XZ`
- size: `82`
- prototype: `CDiagnosticCollection *()`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006fa0`

## callees

- `0x180001074`
- `0x1800064b4`
- `0x180010774`
- `0x180019010`

## pseudocode

```c
CDiagnosticCollection *CreateClassObject<CDiagnosticCollection>()
{
  CDiagnosticCollection *v0; // rax
  CDiagnosticCollection *v1; // rax
  CDiagnosticCollection *v2; // rbx

  v0 = (CDiagnosticCollection *)operator new(0x50u);
  if ( !v0 )
    return 0;
  v1 = CDiagnosticCollection::CDiagnosticCollection(v0);
  v2 = v1;
  if ( v1 && (**((int (__fastcall ***)(__int64))v1 + 1))((__int64)v1 + 8) < 0 )
  {
    (*(void (__fastcall **)(CDiagnosticCollection *))(*(_QWORD *)v2 + 16LL))(v2);
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x1800064b4  push    rbx
0x1800064b6  sub     rsp, 20h
0x1800064ba  mov     ecx, 50h ; 'P'; Size
0x1800064bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800064c4  test    rax, rax
0x1800064c7  jz      short loc_1800064FB
0x1800064c9  mov     rcx, rax; this
0x1800064cc  call    ??0CDiagnosticCollection@@QEAA@XZ; CDiagnosticCollection::CDiagnosticCollection(void)
0x1800064d1  mov     rbx, rax
0x1800064d4  test    rax, rax
0x1800064d7  jz      short loc_1800064FD
0x1800064d9  lea     rcx, [rax+8]
0x1800064dd  mov     rax, [rcx]
0x1800064e0  mov     rax, [rax]
0x1800064e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e8  test    eax, eax
0x1800064ea  jns     short loc_1800064FD
0x1800064ec  mov     rax, [rbx]
0x1800064ef  mov     rcx, rbx
0x1800064f2  mov     rax, [rax+10h]
0x1800064f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064fb  xor     ebx, ebx
0x1800064fd  mov     rax, rbx
0x180006500  add     rsp, 20h
0x180006504  pop     rbx
0x180006505  retn
```
