# CWdsComMetadataBuilder::AppendBinaryEntry(ushort *,uchar *,ulong)

- ea: `0x18000f820`
- end: `0x18000f8d0`
- name: `?AppendBinaryEntry@CWdsComMetadataBuilder@@UEAAJPEAGPEAEK@Z`
- size: `176`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000c2d0`
- `0x18000e3e4`
- `0x18000f820`
- `0x180014d58`
- `0x180014ee0`

## string_xrefs

- `0x18000f861`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f891`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::AppendBinaryEntry(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  unsigned __int64 v5; // rdi
  unsigned int v8; // ebx
  const char *v9; // rdx
  signed int appended; // edi
  const char *v11; // rdx

  v5 = a4;
  v8 = 0;
  if ( (unsigned int)ValidateNonEmptyBstr(a2) && a3 && (_DWORD)v5
    || (v8 = -2147024809,
        (int)ElValidateHr(-2147024809, v9, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x496u) >= 0) )
  {
    appended = CWdsMetadata::AppendBinaryEntry((CWdsComMetadataBuilder *)((char *)this + 64), a2, a3, v5);
    if ( ElValidateWin32(appended, v11, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x49Au) )
    {
      v8 = (unsigned __int16)appended | 0x80070000;
      if ( appended <= 0 )
        return (unsigned int)appended;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000f820  mov     rax, rsp
0x18000f823  mov     [rax+8], rbx
0x18000f827  mov     [rax+10h], rbp
0x18000f82b  mov     [rax+18h], rsi
0x18000f82f  mov     [rax+20h], rdi
0x18000f833  push    r14
0x18000f835  sub     rsp, 20h
0x18000f839  mov     r14, rcx
0x18000f83c  mov     edi, r9d
0x18000f83f  mov     rcx, rdx; pbstr
0x18000f842  mov     rsi, r8
0x18000f845  mov     rbp, rdx
0x18000f848  xor     ebx, ebx
0x18000f84a  call    ValidateNonEmptyBstr
0x18000f84f  test    eax, eax
0x18000f851  jz      short loc_18000F85C
0x18000f853  test    rsi, rsi
0x18000f856  jz      short loc_18000F85C
0x18000f858  test    edi, edi
0x18000f85a  jnz     short loc_18000F879
0x18000f85c  mov     ebx, 80070057h
0x18000f861  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f868  mov     ecx, ebx; int
0x18000f86a  mov     r9d, 496h; unsigned int
0x18000f870  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000f875  test    eax, eax
0x18000f877  js      short loc_18000F8B3
0x18000f879  mov     r9, rdi; unsigned __int64
0x18000f87c  lea     rcx, [r14+40h]; this
0x18000f880  mov     r8, rsi; unsigned __int8 *
0x18000f883  mov     rdx, rbp; unsigned __int16 *
0x18000f886  call    ?AppendBinaryEntry@CWdsMetadata@@QEAAKPEBGPEAE_K@Z; CWdsMetadata::AppendBinaryEntry(ushort const *,uchar *,unsigned __int64)
0x18000f88b  mov     r9d, 49Ah; unsigned int
0x18000f891  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f898  mov     ecx, eax; unsigned int
0x18000f89a  mov     edi, eax
0x18000f89c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000f8a1  test    eax, eax
0x18000f8a3  jz      short loc_18000F8B3
0x18000f8a5  movzx   ebx, di
0x18000f8a8  or      ebx, 80070000h
0x18000f8ae  test    edi, edi
0x18000f8b0  cmovle  ebx, edi
0x18000f8b3  mov     rbp, [rsp+28h+arg_8]
0x18000f8b8  mov     eax, ebx
0x18000f8ba  mov     rbx, [rsp+28h+arg_0]
0x18000f8bf  mov     rsi, [rsp+28h+arg_10]
0x18000f8c4  mov     rdi, [rsp+28h+arg_18]
0x18000f8c9  add     rsp, 20h
0x18000f8cd  pop     r14
0x18000f8cf  retn
```
