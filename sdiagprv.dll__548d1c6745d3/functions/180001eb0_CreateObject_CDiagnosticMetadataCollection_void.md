# CreateObject<CDiagnosticMetadataCollection>(void)

- ea: `0x180001eb0`
- end: `0x180001f02`
- name: `??$CreateObject@VCDiagnosticMetadataCollection@@@@YAPEAUIUnknown@@XZ`
- size: `82`
- prototype: `CDiagnosticMetadataCollection *()`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001074`
- `0x180001eb0`
- `0x1800044e8`
- `0x180019010`

## pseudocode

```c
CDiagnosticMetadataCollection *CreateObject<CDiagnosticMetadataCollection>()
{
  CDiagnosticMetadataCollection *v0; // rax
  CDiagnosticMetadataCollection *v1; // rax
  CDiagnosticMetadataCollection *v2; // rbx

  v0 = (CDiagnosticMetadataCollection *)operator new(0x50u);
  if ( !v0 )
    return 0;
  v1 = CDiagnosticMetadataCollection::CDiagnosticMetadataCollection(v0);
  v2 = v1;
  if ( v1 && (**((int (__fastcall ***)(__int64))v1 + 1))((__int64)v1 + 8) < 0 )
  {
    (*(void (__fastcall **)(CDiagnosticMetadataCollection *))(*(_QWORD *)v2 + 16LL))(v2);
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180001eb0  push    rbx
0x180001eb2  sub     rsp, 20h
0x180001eb6  mov     ecx, 50h ; 'P'; Size
0x180001ebb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001ec0  test    rax, rax
0x180001ec3  jz      short loc_180001EF7
0x180001ec5  mov     rcx, rax; this
0x180001ec8  call    ??0CDiagnosticMetadataCollection@@QEAA@XZ; CDiagnosticMetadataCollection::CDiagnosticMetadataCollection(void)
0x180001ecd  mov     rbx, rax
0x180001ed0  test    rax, rax
0x180001ed3  jz      short loc_180001EF9
0x180001ed5  lea     rcx, [rax+8]
0x180001ed9  mov     rax, [rcx]
0x180001edc  mov     rax, [rax]
0x180001edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ee4  test    eax, eax
0x180001ee6  jns     short loc_180001EF9
0x180001ee8  mov     rax, [rbx]
0x180001eeb  mov     rcx, rbx
0x180001eee  mov     rax, [rax+10h]
0x180001ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ef7  xor     ebx, ebx
0x180001ef9  mov     rax, rbx
0x180001efc  add     rsp, 20h
0x180001f00  pop     rbx
0x180001f01  retn
```
