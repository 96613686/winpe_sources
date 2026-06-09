# CreateClassObject<CDiagnostic>(void)

- ea: `0x1800083ec`
- end: `0x18000843e`
- name: `??$CreateClassObject@VCDiagnostic@@@@YAPEAVCDiagnostic@@XZ`
- size: `82`
- prototype: `CDiagnostic *()`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180008f00`
- `0x18000d418`

## callees

- `0x180001074`
- `0x1800083ec`
- `0x1800133ac`
- `0x180019010`

## pseudocode

```c
CDiagnostic *CreateClassObject<CDiagnostic>()
{
  CDiagnostic *v0; // rax
  CDiagnostic *v1; // rax
  CDiagnostic *v2; // rbx

  v0 = (CDiagnostic *)operator new(0xB0u);
  if ( !v0 )
    return 0;
  v1 = CDiagnostic::CDiagnostic(v0);
  v2 = v1;
  if ( v1 && (**((int (__fastcall ***)(__int64))v1 + 1))((__int64)v1 + 8) < 0 )
  {
    (*(void (__fastcall **)(CDiagnostic *))(*(_QWORD *)v2 + 16LL))(v2);
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x1800083ec  push    rbx
0x1800083ee  sub     rsp, 20h
0x1800083f2  mov     ecx, 0B0h; Size
0x1800083f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800083fc  test    rax, rax
0x1800083ff  jz      short loc_180008433
0x180008401  mov     rcx, rax; this
0x180008404  call    ??0CDiagnostic@@QEAA@XZ; CDiagnostic::CDiagnostic(void)
0x180008409  mov     rbx, rax
0x18000840c  test    rax, rax
0x18000840f  jz      short loc_180008435
0x180008411  lea     rcx, [rax+8]
0x180008415  mov     rax, [rcx]
0x180008418  mov     rax, [rax]
0x18000841b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008420  test    eax, eax
0x180008422  jns     short loc_180008435
0x180008424  mov     rax, [rbx]
0x180008427  mov     rcx, rbx
0x18000842a  mov     rax, [rax+10h]
0x18000842e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008433  xor     ebx, ebx
0x180008435  mov     rax, rbx
0x180008438  add     rsp, 20h
0x18000843c  pop     rbx
0x18000843d  retn
```
