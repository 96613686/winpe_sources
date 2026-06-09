# CWdsMetadataValue::Shutdown(void)

- ea: `0x180009838`
- end: `0x18000988b`
- name: `?Shutdown@CWdsMetadataValue@@QEAAXXZ`
- size: `83`
- prototype: `void __fastcall(CWdsMetadataValue *__hidden this)`
- caller_count: `26`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800042f4`
- `0x180009894`
- `0x180009b3c`
- `0x18000a15c`
- `0x18000a380`
- `0x18000ac50`
- `0x18000b1a8`
- `0x18000b47c`
- `0x18000ba74`
- `0x18000c4e0`
- `0x18000d40c`
- `0x18000fae0`
- `0x18000fcc0`
- `0x18000fe40`
- `0x180010020`
- `0x180010180`
- `0x1800102e0`
- `0x1800105d0`
- `0x180010790`
- `0x1800108e0`
- `0x180010a00`
- `0x180010b60`
- `0x180010c80`
- `0x180010da0`
- `0x180011000`
- `0x1800125c0`

## callees

- `0x180009838`
- `0x1800150b8`

## pseudocode

```c
void __fastcall CWdsMetadataValue::Shutdown(CWdsMetadataValue *this)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( *(_DWORD *)this == 1 )
  {
    v2 = (void *)*((_QWORD *)this + 1);
    if ( v2 )
    {
      operator delete(v2);
      *((_QWORD *)this + 1) = 0;
    }
  }
  else if ( *(_DWORD *)this == 7 )
  {
    v3 = (void *)*((_QWORD *)this + 1);
    if ( v3 )
    {
      operator delete(v3);
      *((_QWORD *)this + 1) = 0;
    }
    *((_QWORD *)this + 2) = 0;
  }
  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x180009838  push    rbx
0x18000983a  sub     rsp, 20h
0x18000983e  cmp     dword ptr [rcx], 1
0x180009841  mov     rbx, rcx
0x180009844  jnz     short loc_18000985B
0x180009846  mov     rcx, [rcx+8]; Block
0x18000984a  test    rcx, rcx
0x18000984d  jz      short loc_180009878
0x18000984f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009854  and     qword ptr [rbx+8], 0
0x180009859  jmp     short loc_180009878
0x18000985b  cmp     dword ptr [rcx], 7
0x18000985e  jnz     short loc_180009878
0x180009860  mov     rcx, [rcx+8]; Block
0x180009864  test    rcx, rcx
0x180009867  jz      short loc_180009873
0x180009869  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000986e  and     qword ptr [rbx+8], 0
0x180009873  and     qword ptr [rbx+10h], 0
0x180009878  and     dword ptr [rbx], 0
0x18000987b  xor     eax, eax
0x18000987d  mov     [rbx+8], rax
0x180009881  mov     [rbx+10h], rax
0x180009885  add     rsp, 20h
0x180009889  pop     rbx
0x18000988a  retn
```
