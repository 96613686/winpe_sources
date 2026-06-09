# _dynamic_initializer_for__s_LFXAPOReg__

- ea: `0x180013210`
- end: `0x1800132c4`
- name: `_dynamic_initializer_for__s_LFXAPOReg__`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180015ea8`

## string_xrefs

- `0x180013237`: `Copyright Microsoft`

## pseudocode

```c
__int64 dynamic_initializer_for__s_LFXAPOReg__()
{
  __int64 result; // rax

  xmmword_1801B7750 = (__int128)CLSID_CWMAudioLFXAPO;
  memset_0(&word_1801B7786, 0, 0x1DEu);
  xmmword_1801B7964 = *(_OWORD *)L"Copyright Microsoft";
  qword_1801B7984 = *(_QWORD *)L"oft";
  xmmword_1801B7974 = *(_OWORD *)L"t Microsoft";
  memset_0(&dword_1801B798C, 0, 0x1D8u);
  result = 1;
  dword_1801B7B7C = -1;
  dword_1801B7B64 = 1;
  xmmword_1801B7B84 = (__int128)GUID_fd7f2b29_24d0_4b5c_b177_592c39f9ca10;
  dword_1801B7B68 = 1;
  dword_1801B7B6C = 1;
  dword_1801B7B70 = 1;
  dword_1801B7B74 = 1;
  dword_1801B7B78 = 1;
  dword_1801B7B80 = 1;
  return result;
}

```

## disassembly

```asm
0x180013210  sub     rsp, 28h
0x180013214  movups  xmm0, xmmword ptr cs:CLSID_CWMAudioLFXAPO.Data1
0x18001321b  xor     edx, edx; Val
0x18001321d  lea     rcx, word_1801B7786; void *
0x180013224  mov     r8d, 1DEh; Size
0x18001322a  movdqu  cs:xmmword_1801B7750, xmm0
0x180013232  call    memset_0
0x180013237  movups  xmm0, xmmword ptr cs:aCopyrightMicro; "Copyright Microsoft"
0x18001323e  xor     edx, edx; Val
0x180013240  mov     r8d, 1D8h; Size
0x180013246  movups  xmm1, xmmword ptr cs:aCopyrightMicro+10h; "t Microsoft"
0x18001324d  lea     rcx, dword_1801B798C; void *
0x180013254  movups  cs:xmmword_1801B7964, xmm0
0x18001325b  movsd   xmm0, qword ptr cs:aCopyrightMicro+20h; "oft"
0x180013263  movsd   cs:qword_1801B7984, xmm0
0x18001326b  movups  cs:xmmword_1801B7974, xmm1
0x180013272  call    memset_0
0x180013277  movups  xmm0, xmmword ptr cs:_GUID_fd7f2b29_24d0_4b5c_b177_592c39f9ca10.Data1
0x18001327e  mov     eax, 1
0x180013283  mov     cs:dword_1801B7B7C, 0FFFFFFFFh
0x18001328d  mov     cs:dword_1801B7B64, eax
0x180013293  movdqu  cs:xmmword_1801B7B84, xmm0
0x18001329b  mov     cs:dword_1801B7B68, eax
0x1800132a1  mov     cs:dword_1801B7B6C, eax
0x1800132a7  mov     cs:dword_1801B7B70, eax
0x1800132ad  mov     cs:dword_1801B7B74, eax
0x1800132b3  mov     cs:dword_1801B7B78, eax
0x1800132b9  mov     cs:dword_1801B7B80, eax
0x1800132bf  add     rsp, 28h
0x1800132c3  retn
```
