# GenerateFileNameForStorage(IContact *,ushort const *,ushort const *,IStream * *,STRW *)

- ea: `0x180012d08`
- end: `0x18001315f`
- name: `?GenerateFileNameForStorage@@YAJPEAUIContact@@PEBG1PEAPEAUIStream@@PEAVSTRW@@@Z`
- size: `1111`
- prototype: `__int64 __usercall@<rax>(struct IContact *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, struct IStream **@<r9>, struct STRW *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18000f2c4`
- `0x1800121f0`

## callees

- `0x180002818`
- `0x180006f7c`
- `0x180008f3c`
- `0x180008f74`
- `0x180009428`
- `0x180009aec`
- `0x18001256c`
- `0x180012d08`
- `0x1800133d0`
- `0x18007a0c8`
- `0x18007a544`
- `0x18007a6d8`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `MSOERT2!OpenFileStreamW` at `0x180013062`
- `MSOERT2!OpenFileStreamW` at `0x180013062`
- `KERNEL32!DeleteFileW` at `0x18001314e`
- `KERNEL32!DeleteFileW` at `0x18001314e`
- `USER32!CharNextW` at `0x180012e4a`
- `USER32!CharNextW` at `0x180012e4a`

## pseudocode

```c
__int64 __fastcall GenerateFileNameForStorage(
        struct IContact *a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IStream **a4,
        void **a5)
{
  int DisplayNameFromContact; // ebx
  WCHAR *v10; // rdx
  WCHAR i; // ax
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // edi
  struct IStream *v15; // rax
  const WCHAR *v16; // rdi
  unsigned int v17; // r15d
  int v18; // esi
  WCHAR *v19; // r14
  const WCHAR *v20; // r9
  int v21; // eax
  int v22; // eax
  const WCHAR *v23; // r9
  LPCWSTR v24; // rcx
  __int64 v26; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v27; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpsz; // [rsp+30h] [rbp-D0h] BYREF
  struct IStream *v29; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v30; // [rsp+40h] [rbp-C0h] BYREF
  void *v31; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v32; // [rsp+60h] [rbp-A0h]
  unsigned int v33; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v35; // [rsp+88h] [rbp-78h]
  _BYTE v36[24]; // [rsp+90h] [rbp-70h] BYREF
  int v37; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v38[264]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v39[64]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v40[144]; // [rsp+340h] [rbp+240h] BYREF
  unsigned __int16 v41[264]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v32 = a3;
  v35 = a2;
  v29 = 0;
  STRW::STRW((STRW *)&v33, v41, 0x104u);
  STRW::STRW((STRW *)&v30, v39, 0x40u);
  BUFFER::BUFFER((BUFFER *)v36, v40, 0x82u);
  v37 = 0;
  lpsz = 0;
  if ( !a1 || !a2 )
    goto LABEL_5;
  if ( a4 )
  {
    *a4 = 0;
  }
  else if ( !a5 )
  {
LABEL_5:
    DisplayNameFromContact = -2147024809;
    goto LABEL_60;
  }
  DisplayNameFromContact = GetDisplayNameFromContact(a1, (struct STRW *)&v30);
  if ( DisplayNameFromContact >= 0 )
  {
    DisplayNameFromContact = RESERVE_STRW::GetWritePointer(
                               (RESERVE_STRW *)v36,
                               (const struct STRW *)&v30,
                               (unsigned __int16 **)&lpsz);
    if ( DisplayNameFromContact >= 0 )
    {
      v10 = (WCHAR *)lpsz;
      if ( lpsz )
      {
        for ( i = *lpsz; i; i = *v10 )
        {
          if ( i > 0x3Cu )
          {
            if ( i == 62 || i == 63 || i == 92 || i == 124 )
LABEL_23:
              *v10 = 95;
          }
          else if ( i == 60 || i == 34 || i == 36 || i == 42 || i == 47 || i == 58 )
          {
            goto LABEL_23;
          }
          v10 = CharNextW(v10);
        }
      }
      memset_0(v31, 0, 2LL * v30);
      v30 = 0;
      DisplayNameFromContact = STRW::TakeAndAppend((STRW *)&v30, (struct RESERVE_STRW *)v36, (unsigned __int16 **)&lpsz);
      if ( DisplayNameFromContact >= 0 )
      {
        v12 = -1;
        v13 = -1;
        do
          ++v13;
        while ( a2[v13] );
        if ( a3 )
        {
          do
            ++v12;
          while ( a3[v12] );
        }
        else
        {
          LODWORD(v12) = 0;
        }
        v14 = v13 + v12 + v30 + 22;
        if ( v14 >= 260 )
        {
          DisplayNameFromContact = RESERVE_STRW::GetWritePointer(
                                     (RESERVE_STRW *)v36,
                                     (const struct STRW *)&v30,
                                     (unsigned __int16 **)&lpsz);
          if ( DisplayNameFromContact < 0 )
            goto LABEL_60;
          lpsz[v30 - v14 + 259] = 0;
          memset_0(v31, 0, 2LL * v30);
          v30 = 0;
          STRW::TakeAndAppend((STRW *)&v30, (struct RESERVE_STRW *)v36, (unsigned __int16 **)&lpsz);
        }
        v15 = v29;
        v16 = &Str;
        v17 = v33;
        v18 = 0;
        v19 = (WCHAR *)lpFileName[0];
        while ( v18 <= 50 )
        {
          memset_0(v38, 0, 0x208u);
          memset_0(v19, 0, 2LL * v17);
          v33 = 0;
          DisplayNameFromContact = STRW::Append((STRW *)&v33, v35);
          if ( DisplayNameFromContact < 0 )
            goto LABEL_60;
          DisplayNameFromContact = STRW::Append((STRW *)&v33, L"\\");
          if ( DisplayNameFromContact < 0 )
            goto LABEL_60;
          if ( v18 )
          {
            if ( v18 >= 40 )
            {
              v22 = OEGetRandom();
              v27 = v32;
              LODWORD(v26) = v22;
            }
            else
            {
              v27 = v32;
              LODWORD(v26) = v18;
            }
            v23 = &Str;
            if ( v30 )
              v23 = (const WCHAR *)v31;
            v21 = StringCchPrintfW(v38, 0x104u, L"%s (%d)%s", v23, v26, v27);
          }
          else
          {
            v20 = &Str;
            if ( v30 )
              v20 = (const WCHAR *)v31;
            v21 = StringCchPrintfW(v38, 0x104u, L"%s%s", v20, v32);
          }
          DisplayNameFromContact = v21;
          if ( v21 < 0 )
            goto LABEL_60;
          DisplayNameFromContact = STRW::Append((STRW *)&v33, v38);
          if ( DisplayNameFromContact < 0 )
            goto LABEL_60;
          v17 = v33;
          v19 = (WCHAR *)lpFileName[0];
          v24 = &Str;
          if ( v33 )
            v24 = lpFileName[0];
          DisplayNameFromContact = OpenFileStreamW(v24, 1, 0x40000000, &v29);
          if ( (int)(DisplayNameFromContact + 0x80000000) >= 0 && DisplayNameFromContact != -2147024816 )
            goto LABEL_60;
          v15 = v29;
          if ( v29 )
            goto LABEL_61;
          ++v18;
        }
        if ( !v15 )
        {
          DisplayNameFromContact = -2147418113;
          goto LABEL_60;
        }
LABEL_61:
        if ( a5 )
        {
          memset_0(a5[1], 0, 2LL * *(unsigned int *)a5);
          *(_DWORD *)a5 = 0;
          DisplayNameFromContact = STRW::Append((STRW *)a5, (const struct STRW *)&v33);
          if ( DisplayNameFromContact < 0 )
            goto LABEL_60;
          v15 = v29;
        }
        if ( a4 )
        {
          *a4 = v15;
          v29 = 0;
        }
        else
        {
          if ( v17 )
            v16 = v19;
          DeleteFileW(v16);
        }
        DisplayNameFromContact = 0;
      }
    }
  }
LABEL_60:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v29);
  v37 = 0;
  BUFFER::ReleaseStorage((BUFFER *)v36);
  v30 = 0;
  BUFFER::ReleaseStorage((BUFFER *)&v31);
  v33 = 0;
  BUFFER::ReleaseStorage((BUFFER *)lpFileName);
  return (unsigned int)DisplayNameFromContact;
}

```

## disassembly

```asm
0x180012d08  push    rbp
0x180012d0a  push    rbx
0x180012d0b  push    rsi
0x180012d0c  push    rdi
0x180012d0d  push    r12
0x180012d0f  push    r13
0x180012d11  push    r14
0x180012d13  push    r15
0x180012d15  lea     rbp, [rsp-4F8h]
0x180012d1d  sub     rsp, 5F8h
0x180012d24  mov     rax, cs:__security_cookie
0x180012d2b  xor     rax, rsp
0x180012d2e  mov     [rbp+530h+var_50], rax
0x180012d35  mov     r12, [rbp+530h+arg_20]
0x180012d3c  mov     rdi, r8
0x180012d3f  mov     [rsp+630h+var_5D0], r8
0x180012d44  mov     rbx, rcx
0x180012d47  mov     rsi, rdx
0x180012d4a  mov     [rbp+530h+var_5A8], rdx
0x180012d4e  xor     r14d, r14d
0x180012d51  lea     rdx, [rbp+530h+var_260]; unsigned __int16 *
0x180012d58  mov     r8d, 104h; unsigned int
0x180012d5e  mov     [rsp+630h+var_5F8], r14
0x180012d63  lea     rcx, [rsp+630h+var_5C8]; this
0x180012d68  mov     r13, r9
0x180012d6b  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180012d70  lea     r8d, [r14+40h]; unsigned int
0x180012d74  lea     rcx, [rsp+630h+var_5F0]; this
0x180012d79  lea     rdx, [rbp+530h+var_370]; unsigned __int16 *
0x180012d80  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180012d85  mov     r8d, 82h; unsigned __int64
0x180012d8b  lea     rcx, [rbp+530h+var_5A0]; this
0x180012d8f  lea     rdx, [rbp+530h+var_2F0]; void *
0x180012d96  call    ??0BUFFER@@QEAA@PEAX_K@Z; BUFFER::BUFFER(void *,unsigned __int64)
0x180012d9b  mov     [rbp+530h+var_588], r14d
0x180012d9f  mov     [rsp+630h+lpsz], r14
0x180012da4  test    rbx, rbx
0x180012da7  jz      short loc_180012DB8
0x180012da9  test    rsi, rsi
0x180012dac  jz      short loc_180012DB8
0x180012dae  test    r13, r13
0x180012db1  jnz     short loc_180012DC2
0x180012db3  test    r12, r12
0x180012db6  jnz     short loc_180012DC6
0x180012db8  mov     ebx, 80070057h
0x180012dbd  jmp     loc_18001309B
0x180012dc2  mov     [r13+0], r14
0x180012dc6  lea     rdx, [rsp+630h+var_5F0]; struct STRW *
0x180012dcb  mov     rcx, rbx; struct IContact *
0x180012dce  call    ?GetDisplayNameFromContact@@YAJPEAUIContact@@PEAVSTRW@@@Z; GetDisplayNameFromContact(IContact *,STRW *)
0x180012dd3  mov     ebx, eax
0x180012dd5  test    eax, eax
0x180012dd7  js      loc_18001309B
0x180012ddd  lea     r8, [rsp+630h+lpsz]; unsigned __int16 **
0x180012de2  lea     rdx, [rsp+630h+var_5F0]; struct STRW *
0x180012de7  lea     rcx, [rbp+530h+var_5A0]; this
0x180012deb  call    ?GetWritePointer@RESERVE_STRW@@QEAAJPEBVSTRW@@PEAPEAG@Z; RESERVE_STRW::GetWritePointer(STRW const *,ushort * *)
0x180012df0  mov     ebx, eax
0x180012df2  test    eax, eax
0x180012df4  js      loc_18001309B
0x180012dfa  mov     rdx, [rsp+630h+lpsz]
0x180012dff  test    rdx, rdx
0x180012e02  jz      short loc_180012E5B
0x180012e04  movzx   eax, word ptr [rdx]
0x180012e07  jmp     short loc_180012E56
0x180012e09  movzx   ecx, ax
0x180012e0c  cmp     ecx, 3Ch ; '<'
0x180012e0f  ja      short loc_180012E2E
0x180012e11  jz      short loc_180012E42
0x180012e13  cmp     ecx, 22h ; '"'
0x180012e16  jz      short loc_180012E42
0x180012e18  cmp     ecx, 24h ; '$'
0x180012e1b  jz      short loc_180012E42
0x180012e1d  cmp     ecx, 2Ah ; '*'
0x180012e20  jz      short loc_180012E42
0x180012e22  cmp     ecx, 2Fh ; '/'
0x180012e25  jz      short loc_180012E42
0x180012e27  cmp     ecx, 3Ah ; ':'
0x180012e2a  jz      short loc_180012E42
0x180012e2c  jmp     short loc_180012E47
0x180012e2e  sub     ecx, 3Eh ; '>'
0x180012e31  jz      short loc_180012E42
0x180012e33  sub     ecx, 1
0x180012e36  jz      short loc_180012E42
0x180012e38  sub     ecx, 1Dh
0x180012e3b  jz      short loc_180012E42
0x180012e3d  cmp     ecx, 20h ; ' '
0x180012e40  jnz     short loc_180012E47
0x180012e42  mov     word ptr [rdx], 5Fh ; '_'
0x180012e47  mov     rcx, rdx; lpsz
0x180012e4a  call    cs:__imp_CharNextW
0x180012e50  mov     rdx, rax
0x180012e53  movzx   eax, word ptr [rax]
0x180012e56  test    ax, ax
0x180012e59  jnz     short loc_180012E09
0x180012e5b  mov     r8d, [rsp+630h+var_5F0]
0x180012e60  xor     edx, edx; Val
0x180012e62  mov     rcx, [rsp+630h+var_5E8]; void *
0x180012e67  add     r8, r8; Size
0x180012e6a  call    memset_0
0x180012e6f  lea     r8, [rsp+630h+lpsz]; unsigned __int16 **
0x180012e74  mov     [rsp+630h+var_5F0], r14d
0x180012e79  lea     rdx, [rbp+530h+var_5A0]; struct RESERVE_STRW *
0x180012e7d  lea     rcx, [rsp+630h+var_5F0]; this
0x180012e82  call    ?TakeAndAppend@STRW@@QEAAJPEAVRESERVE_STRW@@PEAPEAG@Z; STRW::TakeAndAppend(RESERVE_STRW *,ushort * *)
0x180012e87  mov     ebx, eax
0x180012e89  test    eax, eax
0x180012e8b  js      loc_18001309B
0x180012e91  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180012e95  mov     rdx, rcx
0x180012e98  inc     rdx
0x180012e9b  cmp     [rsi+rdx*2], r14w
0x180012ea0  jnz     short loc_180012E98
0x180012ea2  test    rdi, rdi
0x180012ea5  jz      short loc_180012EB3
0x180012ea7  inc     rcx
0x180012eaa  cmp     [rdi+rcx*2], r14w
0x180012eaf  jnz     short loc_180012EA7
0x180012eb1  jmp     short loc_180012EB6
0x180012eb3  mov     rcx, r14
0x180012eb6  mov     edi, [rsp+630h+var_5F0]
0x180012eba  add     edi, 16h
0x180012ebd  add     edi, ecx
0x180012ebf  add     edi, edx
0x180012ec1  cmp     edi, 104h
0x180012ec7  jl      short loc_180012F28
0x180012ec9  lea     r8, [rsp+630h+lpsz]; unsigned __int16 **
0x180012ece  lea     rdx, [rsp+630h+var_5F0]; struct STRW *
0x180012ed3  lea     rcx, [rbp+530h+var_5A0]; this
0x180012ed7  call    ?GetWritePointer@RESERVE_STRW@@QEAAJPEBVSTRW@@PEAPEAG@Z; RESERVE_STRW::GetWritePointer(STRW const *,ushort * *)
0x180012edc  mov     ebx, eax
0x180012ede  test    eax, eax
0x180012ee0  js      loc_18001309B
0x180012ee6  mov     edx, [rsp+630h+var_5F0]
0x180012eea  mov     rax, [rsp+630h+lpsz]
0x180012eef  sub     edx, edi
0x180012ef1  add     edx, 103h
0x180012ef7  mov     [rax+rdx*2], r14w
0x180012efc  xor     edx, edx; Val
0x180012efe  mov     r8d, [rsp+630h+var_5F0]
0x180012f03  mov     rcx, [rsp+630h+var_5E8]; void *
0x180012f08  add     r8, r8; Size
0x180012f0b  call    memset_0
0x180012f10  lea     r8, [rsp+630h+lpsz]; unsigned __int16 **
0x180012f15  mov     [rsp+630h+var_5F0], r14d
0x180012f1a  lea     rdx, [rbp+530h+var_5A0]; struct RESERVE_STRW *
0x180012f1e  lea     rcx, [rsp+630h+var_5F0]; this
0x180012f23  call    ?TakeAndAppend@STRW@@QEAAJPEAVRESERVE_STRW@@PEAPEAG@Z; STRW::TakeAndAppend(RESERVE_STRW *,ushort * *)
0x180012f28  mov     rax, [rsp+630h+var_5F8]
0x180012f2d  lea     rdi, Str
0x180012f34  mov     r15d, [rsp+630h+var_5C8]
0x180012f39  mov     esi, r14d
0x180012f3c  mov     r14, [rsp+630h+lpFileName]
0x180012f41  cmp     esi, 32h ; '2'
0x180012f44  jg      loc_18001308E
0x180012f4a  xor     edx, edx; Val
0x180012f4c  lea     rcx, [rbp+530h+var_580]; void *
0x180012f50  mov     r8d, 208h; Size
0x180012f56  call    memset_0
0x180012f5b  mov     r8d, r15d
0x180012f5e  xor     edx, edx; Val
0x180012f60  add     r8, r8; Size
0x180012f63  mov     rcx, r14; void *
0x180012f66  call    memset_0
0x180012f6b  mov     rdx, [rbp+530h+var_5A8]; unsigned __int16 *
0x180012f6f  lea     rcx, [rsp+630h+var_5C8]; this
0x180012f74  xor     r14d, r14d
0x180012f77  mov     [rsp+630h+var_5C8], r14d
0x180012f7c  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180012f81  mov     ebx, eax
0x180012f83  test    eax, eax
0x180012f85  js      loc_18001309B
0x180012f8b  lea     rdx, asc_18009A90C; "\\"
0x180012f92  lea     rcx, [rsp+630h+var_5C8]; this
0x180012f97  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180012f9c  mov     ebx, eax
0x180012f9e  test    eax, eax
0x180012fa0  js      loc_18001309B
0x180012fa6  test    esi, esi
0x180012fa8  jnz     short loc_180012FD9
0x180012faa  cmp     [rsp+630h+var_5F0], r14d
0x180012faf  lea     r8, aSS_2; "%s%s"
0x180012fb6  mov     rax, [rsp+630h+var_5D0]
0x180012fbb  lea     rcx, [rbp+530h+var_580]; unsigned __int16 *
0x180012fbf  mov     r9, rdi
0x180012fc2  mov     [rsp+630h+var_610], rax
0x180012fc7  cmovnz  r9, [rsp+630h+var_5E8]
0x180012fcd  mov     edx, 104h; unsigned __int64
0x180012fd2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012fd7  jmp     short loc_180013024
0x180012fd9  cmp     esi, 28h ; '('
0x180012fdc  jge     short loc_180012FEE
0x180012fde  mov     rax, [rsp+630h+var_5D0]
0x180012fe3  mov     [rsp+630h+var_608], rax
0x180012fe8  mov     dword ptr [rsp+630h+var_610], esi
0x180012fec  jmp     short loc_180013001
0x180012fee  call    OEGetRandom
0x180012ff3  mov     rcx, [rsp+630h+var_5D0]
0x180012ff8  mov     [rsp+630h+var_608], rcx
0x180012ffd  mov     dword ptr [rsp+630h+var_610], eax
0x180013001  cmp     [rsp+630h+var_5F0], r14d
0x180013006  lea     r8, aSDS; "%s (%d)%s"
0x18001300d  mov     r9, rdi
0x180013010  lea     rcx, [rbp+530h+var_580]; unsigned __int16 *
0x180013014  cmovnz  r9, [rsp+630h+var_5E8]
0x18001301a  mov     edx, 104h; unsigned __int64
0x18001301f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013024  mov     ebx, eax
0x180013026  test    eax, eax
0x180013028  js      short loc_18001309B
0x18001302a  lea     rdx, [rbp+530h+var_580]; unsigned __int16 *
0x18001302e  lea     rcx, [rsp+630h+var_5C8]; this
0x180013033  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x180013038  mov     ebx, eax
0x18001303a  test    eax, eax
0x18001303c  js      short loc_18001309B
0x18001303e  mov     r15d, [rsp+630h+var_5C8]
0x180013043  lea     r9, [rsp+630h+var_5F8]
0x180013048  mov     r14, [rsp+630h+lpFileName]
0x18001304d  test    r15d, r15d
0x180013050  mov     rcx, rdi
0x180013053  mov     edx, 1
0x180013058  cmovnz  rcx, r14
0x18001305c  mov     r8d, 40000000h
0x180013062  call    cs:__imp_OpenFileStreamW
0x180013068  mov     ecx, 80000000h
0x18001306d  mov     ebx, eax
0x18001306f  add     eax, ecx
0x180013071  test    ecx, eax
0x180013073  jnz     short loc_18001307D
0x180013075  cmp     ebx, 80070050h
0x18001307b  jnz     short loc_180013098
0x18001307d  mov     rax, [rsp+630h+var_5F8]
0x180013082  test    rax, rax
0x180013085  jnz     short loc_1800130F5
0x180013087  inc     esi
0x180013089  jmp     loc_180012F41
0x18001308e  test    rax, rax
0x180013091  jnz     short loc_1800130F5
0x180013093  mov     ebx, 8000FFFFh
0x180013098  xor     r14d, r14d
0x18001309b  lea     rcx, [rsp+630h+var_5F8]
0x1800130a0  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800130a5  lea     rcx, [rbp+530h+var_5A0]; this
0x1800130a9  mov     [rbp+530h+var_588], r14d
0x1800130ad  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x1800130b2  lea     rcx, [rsp+630h+var_5E8]; this
0x1800130b7  mov     [rsp+630h+var_5F0], r14d
0x1800130bc  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x1800130c1  lea     rcx, [rsp+630h+lpFileName]; this
0x1800130c6  mov     [rsp+630h+var_5C8], r14d
0x1800130cb  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x1800130d0  mov     eax, ebx
0x1800130d2  mov     rcx, [rbp+530h+var_50]
0x1800130d9  xor     rcx, rsp; StackCookie
0x1800130dc  call    __security_check_cookie
0x1800130e1  add     rsp, 5F8h
0x1800130e8  pop     r15
0x1800130ea  pop     r14
0x1800130ec  pop     r13
0x1800130ee  pop     r12
0x1800130f0  pop     rdi
0x1800130f1  pop     rsi
0x1800130f2  pop     rbx
0x1800130f3  pop     rbp
0x1800130f4  retn
0x1800130f5  test    r12, r12
0x1800130f8  jz      short loc_180013131
0x1800130fa  mov     r8d, [r12]
0x1800130fe  xor     edx, edx; Val
0x180013100  mov     rcx, [r12+8]; void *
0x180013105  add     r8, r8; Size
0x180013108  call    memset_0
0x18001310d  lea     rdx, [rsp+630h+var_5C8]; struct STRW *
0x180013112  mov     dword ptr [r12], 0
0x18001311a  mov     rcx, r12; this
0x18001311d  call    ?Append@STRW@@QEAAJPEBV1@@Z; STRW::Append(STRW const *)
0x180013122  mov     ebx, eax
0x180013124  test    eax, eax
0x180013126  js      loc_180013098
0x18001312c  mov     rax, [rsp+630h+var_5F8]
0x180013131  test    r13, r13
0x180013134  jz      short loc_180013144
0x180013136  xor     r14d, r14d
0x180013139  mov     [r13+0], rax
0x18001313d  mov     [rsp+630h+var_5F8], r14
0x180013142  jmp     short loc_180013157
0x180013144  test    r15d, r15d
0x180013147  cmovnz  rdi, r14
0x18001314b  mov     rcx, rdi; lpFileName
0x18001314e  call    cs:__imp_DeleteFileW
0x180013154  xor     r14d, r14d
0x180013157  mov     ebx, r14d
0x18001315a  jmp     loc_18001309B
```
