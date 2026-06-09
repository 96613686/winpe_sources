# CWdsMetadata::GetByIndex(ulong,CWdsMetadataEntry const * *)

- ea: `0x18000ad94`
- end: `0x18000aded`
- name: `?GetByIndex@CWdsMetadata@@QEBAKKPEAPEBVCWdsMetadataEntry@@@Z`
- size: `89`
- prototype: `unsigned int(CWdsMetadata *__hidden this, unsigned int, const struct CWdsMetadataEntry **)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800062f0`
- `0x18000b228`
- `0x18000b834`
- `0x18000dab4`
- `0x18000e750`
- `0x1800114a4`

## callees

- `0x18000ad94`
- `0x180014d58`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::GetByIndex(CWdsMetadata *this, const char *a2, const struct CWdsMetadataEntry **a3)
{
  const struct CWdsMetadataEntry *v3; // rdi
  unsigned int v4; // ebx

  v3 = 0;
  v4 = 0;
  if ( (unsigned int)a2 < *((_DWORD *)this + 15) )
  {
    a2 = (const char *)(unsigned int)a2;
    v3 = *(const struct CWdsMetadataEntry **)(*((_QWORD *)this + 6) + 8LL * (unsigned int)a2);
  }
  else
  {
    v4 = 1413;
  }
  if ( !(unsigned int)ElValidateWin32(v4, a2, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0xDBBu) )
    *a3 = v3;
  return v4;
}

```

## disassembly

```asm
0x18000ad94  mov     [rsp+arg_0], rbx
0x18000ad99  mov     [rsp+arg_8], rsi
0x18000ad9e  push    rdi
0x18000ad9f  sub     rsp, 20h
0x18000ada3  xor     edi, edi
0x18000ada5  xor     ebx, ebx
0x18000ada7  mov     rsi, r8
0x18000adaa  cmp     edx, [rcx+3Ch]
0x18000adad  jb      short loc_18000ADB6
0x18000adaf  mov     ebx, 585h
0x18000adb4  jmp     short loc_18000ADC0
0x18000adb6  mov     rcx, [rcx+30h]
0x18000adba  mov     edx, edx; char *
0x18000adbc  mov     rdi, [rcx+rdx*8]
0x18000adc0  mov     r9d, 0DBBh; unsigned int
0x18000adc6  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000adcd  mov     ecx, ebx; unsigned int
0x18000adcf  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000add4  test    eax, eax
0x18000add6  jnz     short loc_18000ADDB
0x18000add8  mov     [rsi], rdi
0x18000addb  mov     rsi, [rsp+28h+arg_8]
0x18000ade0  mov     eax, ebx
0x18000ade2  mov     rbx, [rsp+28h+arg_0]
0x18000ade7  add     rsp, 20h
0x18000adeb  pop     rdi
0x18000adec  retn
```
