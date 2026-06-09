# CreateClassObject<CDiagnosticMetadata>(void)

- ea: `0x18000101c`
- end: `0x18000106e`
- name: `??$CreateClassObject@VCDiagnosticMetadata@@@@YAPEAVCDiagnosticMetadata@@XZ`
- size: `82`
- prototype: `CDiagnosticMetadata *()`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x18000101c`
- `0x180001074`
- `0x1800035cc`
- `0x180019010`

## pseudocode

```c
CDiagnosticMetadata *CreateClassObject<CDiagnosticMetadata>()
{
  CDiagnosticMetadata *v0; // rax
  CDiagnosticMetadata *v1; // rax
  CDiagnosticMetadata *v2; // rbx

  v0 = (CDiagnosticMetadata *)operator new(0x58u);
  if ( !v0 )
    return 0;
  v1 = CDiagnosticMetadata::CDiagnosticMetadata(v0);
  v2 = v1;
  if ( v1 && (**((int (__fastcall ***)(__int64))v1 + 1))((__int64)v1 + 8) < 0 )
  {
    (*(void (__fastcall **)(CDiagnosticMetadata *))(*(_QWORD *)v2 + 16LL))(v2);
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18000101c  push    rbx
0x18000101e  sub     rsp, 20h
0x180001022  mov     ecx, 58h ; 'X'; Size
0x180001027  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000102c  test    rax, rax
0x18000102f  jz      short loc_180001063
0x180001031  mov     rcx, rax; this
0x180001034  call    ??0CDiagnosticMetadata@@QEAA@XZ; CDiagnosticMetadata::CDiagnosticMetadata(void)
0x180001039  mov     rbx, rax
0x18000103c  test    rax, rax
0x18000103f  jz      short loc_180001065
0x180001041  lea     rcx, [rax+8]
0x180001045  mov     rax, [rcx]
0x180001048  mov     rax, [rax]
0x18000104b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001050  test    eax, eax
0x180001052  jns     short loc_180001065
0x180001054  mov     rax, [rbx]
0x180001057  mov     rcx, rbx
0x18000105a  mov     rax, [rax+10h]
0x18000105e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001063  xor     ebx, ebx
0x180001065  mov     rax, rbx
0x180001068  add     rsp, 20h
0x18000106c  pop     rbx
0x18000106d  retn
```
