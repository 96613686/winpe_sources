# CExtensionExclusionsPolicy::Init(void)

- ea: `0x180010034`
- end: `0x180010206`
- name: `?Init@CExtensionExclusionsPolicy@@QEAAJXZ`
- size: `466`
- prototype: `__int64 __fastcall(CExtensionExclusionsPolicy *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001020c`

## callees

- `0x180005cc0`
- `0x18000957c`
- `0x18000eaac`
- `0x180010034`
- `0x180010544`
- `0x180010b4c`
- `0x180010c18`
- `0x180013bd8`
- `0x18001a7fc`
- `0x18001a828`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180010182`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180010182`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010116`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010116`

## pseudocode

```c
__int64 __fastcall CExtensionExclusionsPolicy::Init(CExtensionExclusionsPolicy *this)
{
  void *v2; // rcx
  int v3; // eax
  wchar_t *v4; // r14
  int v5; // ebx
  unsigned __int16 *v6; // r13
  char *v7; // r12
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rsi
  const wchar_t *v11; // r15
  const wchar_t *v12; // rax
  size_t v13; // r13
  unsigned __int64 v14; // rdx
  int v15; // eax
  unsigned int v16; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v17; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v19; // [rsp+40h] [rbp-C0h]
  int v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+58h] [rbp-A8h]
  int v23; // [rsp+60h] [rbp-A0h]
  LPVOID pv; // [rsp+68h] [rbp-98h]
  unsigned __int16 v25[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SrcStr; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v27[263]; // [rsp+282h] [rbp+182h] BYREF

  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v21 = *(_QWORD *)this;
  v22 = *((_QWORD *)this + 1);
  v20 = 0;
  v23 = 1;
  pv = 0;
  v3 = CTRegValue<unsigned short *>::ReadFromReg((__int64)&v20);
  v4 = (wchar_t *)pv;
  v5 = v3;
  if ( v3 >= 0 )
  {
    if ( v20 )
    {
      v17 = 0;
      v5 = StringCchLengthW((const unsigned __int16 *)pv, 0x7FFFFFFCu, (unsigned __int64 *)&v17);
      if ( v5 >= 0 )
      {
        v6 = v17;
        v7 = (char *)v17 + 3;
        v18 = (unsigned __int64)v17 + 3;
        v8 = (unsigned __int16 *)operator new(saturated_mul((unsigned __int64)v17 + 3, 2u));
        v9 = v8;
        if ( v8 )
        {
          v17 = v8;
          *v8 = 0;
          v5 = StringCchCopyW(v8, (unsigned __int64)v7, L";");
          v11 = v4;
          v12 = &v4[(_QWORD)v6];
          v19 = v12;
          while ( v5 >= 0 )
          {
            if ( v11 >= v12 )
            {
              *((_QWORD *)this + 2) = v9;
              goto LABEL_9;
            }
            v13 = wcscspn(v11, L";");
            if ( (int)StringCchCopyNW(v25, 0x104u, v11, v13) >= 0
              && (int)CExtensionExclusionsPolicy::Normalize(&SrcStr, v14, v25) >= 0 )
            {
              v15 = StringCchCatExW(v17, (unsigned __int64)v7, v27, &v17, &v18, v16);
              v7 = (char *)v18;
              v5 = v15;
            }
            v12 = v19;
            v11 += v13 + 1;
          }
        }
        else
        {
          v5 = -2147024882;
        }
        operator delete(v9);
      }
    }
  }
LABEL_9:
  CoTaskMemFree(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180010034  push    rbp
0x180010036  push    rbx
0x180010037  push    rsi
0x180010038  push    rdi
0x180010039  push    r12
0x18001003b  push    r13
0x18001003d  push    r14
0x18001003f  push    r15
0x180010041  lea     rbp, [rsp-3A8h]
0x180010049  sub     rsp, 4A8h
0x180010050  mov     rax, cs:__security_cookie
0x180010057  xor     rax, rsp
0x18001005a  mov     [rbp+3E0h+var_50], rax
0x180010061  mov     rdi, rcx
0x180010064  xor     r15d, r15d
0x180010067  mov     rcx, [rcx+10h]; lpMem
0x18001006b  test    rcx, rcx
0x18001006e  jz      short loc_180010079
0x180010070  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010075  mov     [rdi+10h], r15
0x180010079  mov     rax, [rdi]
0x18001007c  lea     rcx, [rsp+4E0h+var_498]
0x180010081  mov     [rsp+4E0h+var_490], rax
0x180010086  mov     rax, [rdi+8]
0x18001008a  mov     [rsp+4E0h+var_488], rax
0x18001008f  mov     [rsp+4E0h+var_498], r15d
0x180010094  mov     [rsp+4E0h+var_480], 1
0x18001009c  mov     [rsp+4E0h+pv], r15
0x1800100a1  call    ?ReadFromReg@?$CTRegValue@PEAG@@QEAAJXZ; CTRegValue<ushort *>::ReadFromReg(void)
0x1800100a6  mov     r14, [rsp+4E0h+pv]
0x1800100ab  mov     ebx, eax
0x1800100ad  test    eax, eax
0x1800100af  js      short loc_180010113
0x1800100b1  cmp     [rsp+4E0h+var_498], r15d
0x1800100b6  jz      short loc_180010113
0x1800100b8  lea     r8, [rsp+4E0h+var_4B0]; unsigned __int64 *
0x1800100bd  mov     [rsp+4E0h+var_4B0], r15
0x1800100c2  mov     edx, 7FFFFFFCh; unsigned __int64
0x1800100c7  mov     rcx, r14; unsigned __int16 *
0x1800100ca  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800100cf  mov     ebx, eax
0x1800100d1  test    eax, eax
0x1800100d3  js      short loc_180010113
0x1800100d5  mov     r13, [rsp+4E0h+var_4B0]
0x1800100da  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800100e1  mov     eax, 2
0x1800100e6  lea     r12, [r13+3]
0x1800100ea  mul     r12
0x1800100ed  mov     [rsp+4E0h+var_4A8], r12
0x1800100f2  cmovb   rax, rcx
0x1800100f6  mov     rcx, rax; unsigned __int64
0x1800100f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800100fe  mov     rsi, rax
0x180010101  test    rax, rax
0x180010104  jnz     short loc_180010141
0x180010106  mov     ebx, 8007000Eh
0x18001010b  mov     rcx, rsi; lpMem
0x18001010e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010113  mov     rcx, r14; pv
0x180010116  call    cs:__imp_CoTaskMemFree
0x18001011c  mov     eax, ebx
0x18001011e  mov     rcx, [rbp+3E0h+var_50]
0x180010125  xor     rcx, rsp; StackCookie
0x180010128  call    __security_check_cookie
0x18001012d  add     rsp, 4A8h
0x180010134  pop     r15
0x180010136  pop     r14
0x180010138  pop     r13
0x18001013a  pop     r12
0x18001013c  pop     rdi
0x18001013d  pop     rsi
0x18001013e  pop     rbx
0x18001013f  pop     rbp
0x180010140  retn
0x180010141  lea     r8, pszSrc; ";"
0x180010148  mov     [rsp+4E0h+var_4B0], rsi
0x18001014d  mov     rdx, r12; unsigned __int64
0x180010150  mov     [rax], r15w
0x180010154  mov     rcx, rsi; unsigned __int16 *
0x180010157  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001015c  mov     ebx, eax
0x18001015e  mov     r15, r14
0x180010161  lea     rax, [r14+r13*2]
0x180010165  mov     [rsp+4E0h+var_4A0], rax
0x18001016a  jmp     loc_1800101F0
0x18001016f  cmp     r15, rax
0x180010172  jnb     loc_1800101FD
0x180010178  lea     rdx, pszSrc; ";"
0x18001017f  mov     rcx, r15; String
0x180010182  call    cs:__imp_wcscspn
0x180010188  mov     r8, r15; unsigned __int16 *
0x18001018b  lea     rcx, [rsp+4E0h+var_470]; unsigned __int16 *
0x180010190  mov     r9, rax; unsigned __int64
0x180010193  mov     edx, 104h; unsigned __int64
0x180010198  mov     r13, rax
0x18001019b  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800101a0  test    eax, eax
0x1800101a2  js      short loc_1800101E3
0x1800101a4  lea     r8, [rsp+4E0h+var_470]; unsigned __int16 *
0x1800101a9  lea     rcx, [rbp+3E0h+SrcStr]; lpSrcStr
0x1800101b0  call    ?Normalize@CExtensionExclusionsPolicy@@SAJPEAG_KPEBG@Z; CExtensionExclusionsPolicy::Normalize(ushort *,unsigned __int64,ushort const *)
0x1800101b5  test    eax, eax
0x1800101b7  js      short loc_1800101E3
0x1800101b9  mov     rcx, [rsp+4E0h+var_4B0]; unsigned __int16 *
0x1800101be  lea     rax, [rsp+4E0h+var_4A8]
0x1800101c3  lea     r9, [rsp+4E0h+var_4B0]; unsigned __int16 **
0x1800101c8  mov     [rsp+4E0h+var_4C0], rax; unsigned __int64 *
0x1800101cd  lea     r8, [rbp+3E0h+var_25E]; unsigned __int16 *
0x1800101d4  mov     rdx, r12; unsigned __int64
0x1800101d7  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800101dc  mov     r12, [rsp+4E0h+var_4A8]
0x1800101e1  mov     ebx, eax
0x1800101e3  mov     rax, [rsp+4E0h+var_4A0]
0x1800101e8  lea     r15, [r15+r13*2]
0x1800101ec  add     r15, 2
0x1800101f0  test    ebx, ebx
0x1800101f2  jns     loc_18001016F
0x1800101f8  jmp     loc_18001010B
0x1800101fd  mov     [rdi+10h], rsi
0x180010201  jmp     loc_180010113
```
