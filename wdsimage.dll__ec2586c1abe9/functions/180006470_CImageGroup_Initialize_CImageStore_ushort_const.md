# CImageGroup::Initialize(CImageStore *,ushort const *)

- ea: `0x180006470`
- end: `0x18000653c`
- name: `?Initialize@CImageGroup@@QEAAJPEAVCImageStore@@PEBG@Z`
- size: `204`
- prototype: `__int64 __fastcall(CImageGroup *__hidden this, struct CImageStore *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800062a0`
- `0x180006d60`
- `0x180006e70`
- `0x180007720`

## callees

- `0x180006470`
- `0x180006714`
- `0x180006810`
- `0x18000dc28`

## import_xrefs

- `WdsCommonLib!WdsDirectoryExists` at `0x1800064cc`
- `WdsCommonLib!WdsDirectoryExists` at `0x1800064cc`
- `WdsCommonLib!ConcatenatePaths` at `0x18000649b`
- `WdsCommonLib!ConcatenatePaths` at `0x18000649b`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800064ea`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800064ea`

## pseudocode

```c
__int64 __fastcall CImageGroup::Initialize(unsigned __int16 **this, struct CImageStore *a2, const unsigned __int16 *a3)
{
  LPCWSTR *v3; // rdi
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8

  v3 = (LPCWSTR *)(this + 4);
  v6 = (unsigned int)ConcatenatePaths(*((_QWORD *)a2 + 3), a3, this + 4);
  if ( !(unsigned int)ElValidateWin32_0(v6, v7, v8, 127) )
  {
    if ( !(unsigned int)WdsDirectoryExists(*v3) )
    {
      LODWORD(v6) = -1056833012;
      return (unsigned int)v6;
    }
    LODWORD(v6) = DuplicateStringW(a3, this + 3);
    if ( !(unsigned int)ElValidateWin32_0((unsigned int)v6, v9, v10, 142) )
    {
      LODWORD(v6) = pWdsImgGetSecurity(*v3, this + 5);
      ElValidateHr_1((unsigned int)v6, v11, v12, 148);
      return (unsigned int)v6;
    }
  }
  if ( (int)v6 > 0 )
    LODWORD(v6) = (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006470  mov     [rsp+arg_0], rbx
0x180006475  mov     [rsp+arg_8], rbp
0x18000647a  mov     [rsp+arg_10], rsi
0x18000647f  push    rdi
0x180006480  sub     rsp, 20h
0x180006484  mov     rax, rdx
0x180006487  lea     rdi, [rcx+20h]
0x18000648b  mov     rbp, r8
0x18000648e  mov     rsi, rcx
0x180006491  mov     r8, rdi
0x180006494  mov     rdx, rbp
0x180006497  mov     rcx, [rax+18h]
0x18000649b  call    cs:__imp_ConcatenatePaths
0x1800064a2  nop     dword ptr [rax+rax+00h]
0x1800064a7  mov     ecx, eax
0x1800064a9  mov     r9d, 7Fh
0x1800064af  mov     ebx, eax
0x1800064b1  call    ElValidateWin32_0
0x1800064b6  test    eax, eax
0x1800064b8  jz      short loc_1800064C9
0x1800064ba  test    ebx, ebx
0x1800064bc  jle     short loc_180006524
0x1800064be  movzx   ebx, bx
0x1800064c1  or      ebx, 80070000h
0x1800064c7  jmp     short loc_180006524
0x1800064c9  mov     rcx, [rdi]
0x1800064cc  call    cs:__imp_WdsDirectoryExists
0x1800064d3  nop     dword ptr [rax+rax+00h]
0x1800064d8  test    eax, eax
0x1800064da  jnz     short loc_1800064E3
0x1800064dc  mov     ebx, 0C102020Ch
0x1800064e1  jmp     short loc_180006524
0x1800064e3  lea     rdx, [rsi+18h]
0x1800064e7  mov     rcx, rbp
0x1800064ea  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800064f1  nop     dword ptr [rax+rax+00h]
0x1800064f6  mov     ecx, eax
0x1800064f8  mov     r9d, 8Eh
0x1800064fe  mov     ebx, eax
0x180006500  call    ElValidateWin32_0
0x180006505  test    eax, eax
0x180006507  jnz     short loc_1800064BA
0x180006509  mov     rcx, [rdi]; lpFileName
0x18000650c  lea     rdx, [rsi+28h]; unsigned __int16 **
0x180006510  call    ?pWdsImgGetSecurity@@YAJPEAGPEAPEAG@Z; pWdsImgGetSecurity(ushort *,ushort * *)
0x180006515  mov     r9d, 94h
0x18000651b  mov     ecx, eax
0x18000651d  mov     ebx, eax
0x18000651f  call    ElValidateHr_1
0x180006524  mov     rbp, [rsp+28h+arg_8]
0x180006529  mov     eax, ebx
0x18000652b  mov     rbx, [rsp+28h+arg_0]
0x180006530  mov     rsi, [rsp+28h+arg_10]
0x180006535  add     rsp, 20h
0x180006539  pop     rdi
0x18000653a  retn
```
