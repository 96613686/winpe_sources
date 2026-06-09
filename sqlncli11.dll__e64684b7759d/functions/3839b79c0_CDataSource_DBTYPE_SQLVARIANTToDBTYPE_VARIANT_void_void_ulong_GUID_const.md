# CDataSource::DBTYPE_SQLVARIANTToDBTYPE_VARIANT(void *,void *,ulong *,_GUID const *)

- ea: `0x3839b79c0`
- end: `0x3839b80c1`
- name: `?DBTYPE_SQLVARIANTToDBTYPE_VARIANT@CDataSource@@QEAAJPEAX0PEAKPEBU_GUID@@@Z`
- size: `1793`
- prototype: `__int64 __fastcall(CDataSource *this, char *, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x383a0baf0`

## callees

- `0x3838427d0`
- `0x3838434c0`
- `0x383845400`
- `0x38385b340`
- `0x38391aed0`
- `0x38391afe0`
- `0x3839b1b00`
- `0x3839b79c0`
- `0x3839ba1c0`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x3839b7c7f`
- `KERNEL32!MultiByteToWideChar` at `0x3839b7d4d`
- `KERNEL32!MultiByteToWideChar` at `0x3839b7c7f`
- `KERNEL32!MultiByteToWideChar` at `0x3839b7d4d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x3839b7bbb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x3839b7cd9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x3839b7bbb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x3839b7cd9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x3839b7dd9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x3839b7dd9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x3839b7e47`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x3839b7e47`
- `OLEAUT32!__imp_VarDecFromStr` at `0x3839b7f2c`
- `OLEAUT32!__imp_VarDecFromStr` at `0x3839b7f2c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x3839b7d6d`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x3839b7d6d`

## pseudocode

```c
__int64 __fastcall CDataSource::DBTYPE_SQLVARIANTToDBTYPE_VARIANT(
        CDataSource *this,
        char *a2,
        void *a3,
        unsigned int *a4)
{
  int v4; // eax
  unsigned int v8; // ebx
  double v9; // xmm1_8
  double v10; // xmm0_8
  double v11; // xmm0_8
  BSTR v12; // rax
  int v13; // eax
  UINT v14; // ecx
  UINT v15; // eax
  int cchWideChar; // ebp
  WCHAR *lpWideCharStr; // rax
  SAFEARRAY *Vector; // rax
  unsigned int v19; // eax
  VARIANTARG *v20; // rcx
  char v21; // al
  unsigned __int16 v22; // dx
  unsigned __int8 v24; // [rsp+58h] [rbp-280h]
  unsigned int v25; // [rsp+78h] [rbp-260h]
  unsigned int v26; // [rsp+80h] [rbp-258h] BYREF
  UINT CodePage; // [rsp+84h] [rbp-254h] BYREF
  _DWORD v28[2]; // [rsp+88h] [rbp-250h] BYREF
  void *ppvData; // [rsp+90h] [rbp-248h] BYREF
  unsigned __int64 v30; // [rsp+98h] [rbp-240h] BYREF
  OLECHAR strIn[264]; // [rsp+A0h] [rbp-238h] BYREF

  v4 = *(unsigned __int16 *)a2;
  v8 = 0;
  v26 = 0;
  switch ( v4 )
  {
    case 0:
      *(_WORD *)a3 = 0;
      return v8;
    case 1:
      *(_WORD *)a3 = 1;
      return v8;
    case 2:
      *(_WORD *)a3 = 2;
      *((_WORD *)a3 + 4) = *((_WORD *)a2 + 8);
      return v8;
    case 3:
      *(_WORD *)a3 = 3;
      *((_DWORD *)a3 + 2) = *((_DWORD *)a2 + 4);
      return v8;
    case 4:
      *(_WORD *)a3 = 4;
      *((_DWORD *)a3 + 2) = *((_DWORD *)a2 + 4);
      return v8;
    case 5:
      *(_WORD *)a3 = 5;
      *((_QWORD *)a3 + 1) = *((_QWORD *)a2 + 2);
      return v8;
    case 6:
    case 200:
      *(_WORD *)a3 = 6;
      *((_QWORD *)a3 + 1) = *((_QWORD *)a2 + 2);
      return v8;
    case 11:
      *(_WORD *)a3 = 11;
      *((_WORD *)a3 + 4) = *((_WORD *)a2 + 8);
      return v8;
    case 17:
      *(_WORD *)a3 = 17;
      *((_BYTE *)a3 + 8) = a2[16];
      return v8;
    case 20:
      *(_WORD *)a3 = 20;
      *((_QWORD *)a3 + 1) = *((_QWORD *)a2 + 2);
      return v8;
    case 131:
    case 205:
      *(_WORD *)a3 = 14;
      v30 = 0;
      if ( (int)_VarStrFromNum((const struct tagDB_NUMERIC *)(a2 + 16), strIn, &v30, 0x383800000uLL) >= 0 )
      {
        v8 = VarDecFromStr(strIn, 0x409u, 0, (DECIMAL *)a3);
        if ( (v8 & 0x80000000) != 0 )
        {
          v8 = -2147467259;
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( off_383B49128[0] )
              bidTraceW(off_383B43258[0], 7227433, off_383B49128[0], 2147500037LL);
          }
        }
      }
      else
      {
        v8 = -2147467259;
        if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
          bidTraceW(off_383B43258[0], 7221289, off_383B49128[0], 2147500037LL);
      }
      return v8;
    case 133:
      v19 = CDataSource::DataConvert(
              this,
              0x85u,
              12,
              4,
              0,
              (VARIANTARG *)(a2 + 16),
              (char *)a3,
              0x18u,
              0,
              (unsigned __int8 *)&v26,
              10,
              0,
              0,
              0,
              0,
              0);
      goto LABEL_61;
    case 135:
    case 206:
      *(_WORD *)a3 = 7;
      if ( DateTimeFromTimestamp((struct tagDBTIMESTAMP *)a2 + 1, 8u, v28, 0) )
      {
        v8 = -2147467259;
        if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
          bidTraceW(off_383B43258[0], 7091241, off_383B49128[0], 2147500037LL);
      }
      else
      {
        v9 = (double)v28[1] / 25920000.0;
        v10 = (double)(v28[0] + 2);
        if ( v10 < 0.0 )
          v11 = v10 - v9;
        else
          v11 = v10 + v9;
        *((double *)a3 + 1) = v11;
      }
      return v8;
    case 145:
      v25 = 0;
      v20 = (VARIANTARG *)(a2 + 16);
      v24 = a2[28];
      v21 = *((_BYTE *)&qword_383911F98[8] + v24);
      v22 = 145;
      goto LABEL_60;
    case 146:
      v25 = 0;
      v20 = (VARIANTARG *)(a2 + 16);
      v24 = a2[36];
      v21 = *((_BYTE *)&qword_383911F98[7] + v24);
      v22 = 146;
      goto LABEL_60;
    case 201:
    case 202:
      *(_WORD *)a3 = 8;
      v12 = SysAllocStringLen(*((const OLECHAR **)a2 + 3), (unsigned __int64)*((__int16 *)a2 + 8) >> 1);
      *((_QWORD *)a3 + 1) = v12;
      if ( !v12 )
      {
        v8 = -2147024882;
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_383B49128[0] )
            bidTraceW(off_383B43258[0], 7117865, off_383B49128[0], 2147942414LL);
        }
      }
      return v8;
    case 203:
    case 204:
      CodePage = 0;
      v13 = CodePageFromTDSCollation((int)a2 + 32, (unsigned int)&CodePage, (_DWORD)a3, 0x83800000);
      v8 = v13;
      if ( v13 >= 0 )
      {
        v14 = CodePage;
        *(_WORD *)a3 = 8;
        v15 = MultiByteToWideChar(v14, 0, *((LPCCH *)a2 + 3), *((__int16 *)a2 + 8), 0, 0);
        cchWideChar = v15;
        if ( v15 )
        {
          lpWideCharStr = SysAllocStringLen(0, v15);
          *((_QWORD *)a3 + 1) = lpWideCharStr;
          if ( lpWideCharStr )
          {
            MultiByteToWideChar(CodePage, 0, *((LPCCH *)a2 + 3), *((__int16 *)a2 + 8), lpWideCharStr, cchWideChar);
          }
          else
          {
            v8 = -2147024882;
            if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
              bidTraceW(off_383B43258[0], 7157801, off_383B49128[0], 2147942414LL);
          }
        }
        else
        {
          v8 = -2147467259;
          if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
            bidTraceW(off_383B43258[0], 7149609, off_383B49128[0], 2147500037LL);
        }
      }
      else if ( (bidGblFlags & 2) != 0 )
      {
        bidTraceHR(off_383B43258[0], 7135241, (unsigned int)v13);
      }
      return v8;
    case 207:
    case 208:
      *(_WORD *)a3 = 8209;
      Vector = SafeArrayCreateVector(0x11u, 0, *((__int16 *)a2 + 8));
      *((_QWORD *)a3 + 1) = Vector;
      if ( Vector )
      {
        ppvData = 0;
        if ( SafeArrayAccessData(Vector, &ppvData) >= 0 )
        {
          memcpy(ppvData, *((const void **)a2 + 3), *((__int16 *)a2 + 8));
          v8 = SafeArrayUnaccessData(*((SAFEARRAY **)a3 + 1));
          if ( (v8 & 0x80000000) != 0 )
          {
            v8 = -2147467259;
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( off_383B49128[0] )
                bidTraceW(off_383B43258[0], 7204905, off_383B49128[0], 2147500037LL);
            }
          }
        }
        else
        {
          v8 = -2147467259;
          if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
            bidTraceW(off_383B43258[0], 7193641, off_383B49128[0], 2147500037LL);
        }
      }
      else
      {
        v8 = -2147024882;
        if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
          bidTraceW(off_383B43258[0], 7185449, off_383B49128[0], 2147942414LL);
      }
      return v8;
    case 212:
      v25 = 1024;
      v20 = (VARIANTARG *)(a2 + 16);
      v24 = a2[32];
      v21 = *((_BYTE *)&qword_383911F98[9] + v24);
      v22 = 135;
LABEL_60:
      v19 = CDataSource::DataConvert(
              this,
              v22,
              12,
              4,
              0,
              v20,
              (char *)a3,
              0x18u,
              0,
              (unsigned __int8 *)&v26,
              v21,
              v24,
              0,
              0,
              0,
              v25);
LABEL_61:
      v8 = v19;
      break;
    default:
      return v8;
  }
  return v8;
}

```

## disassembly

```asm
0x3839b79c0  mov     [rsp+arg_18], rbx
0x3839b79c5  push    rbp
0x3839b79c6  push    rsi
0x3839b79c7  push    rdi
0x3839b79c8  sub     rsp, 2C0h
0x3839b79cf  mov     rax, cs:__security_cookie
0x3839b79d6  xor     rax, rsp
0x3839b79d9  mov     [rsp+2D8h+var_28], rax
0x3839b79e1  movzx   eax, word ptr [rdx]
0x3839b79e4  xor     ebp, ebp
0x3839b79e6  mov     rdi, r8
0x3839b79e9  mov     rsi, rdx
0x3839b79ec  mov     r10, rcx
0x3839b79ef  mov     ebx, ebp
0x3839b79f1  mov     [rsp+2D8h+var_258], ebp
0x3839b79f8  cmp     eax, 0D4h; switch 213 cases
0x3839b79fd  ja      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7a03  lea     r9, cs:383800000h; unsigned __int64
0x3839b7a0a  movzx   eax, ds:(byte_3839B8114 - 383800000h)[r9+rax]
0x3839b7a13  mov     ecx, ds:(jpt_3839B7A1E - 383800000h)[r9+rax*4]
0x3839b7a1b  add     rcx, r9
0x3839b7a1e  jmp     rcx; switch jump
0x3839b7a20  mov     eax, 1; jumptable 00000003839B7A1E case 1
0x3839b7a25  mov     [r8], ax
0x3839b7a29  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7a2e  mov     [r8], bp; jumptable 00000003839B7A1E case 0
0x3839b7a32  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7a37  mov     ecx, 11h; jumptable 00000003839B7A1E case 17
0x3839b7a3c  mov     [r8], cx
0x3839b7a40  movzx   eax, byte ptr [rdx+10h]
0x3839b7a44  mov     [r8+8], al
0x3839b7a48  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7a4d  mov     eax, 2; jumptable 00000003839B7A1E case 2
0x3839b7a52  mov     [r8], ax
0x3839b7a56  movzx   eax, word ptr [rdx+10h]
0x3839b7a5a  mov     [r8+8], ax
0x3839b7a5f  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7a64  mov     eax, 3; jumptable 00000003839B7A1E case 3
0x3839b7a69  mov     [r8], ax
0x3839b7a6d  mov     eax, [rdx+10h]
0x3839b7a70  mov     [r8+8], eax
0x3839b7a74  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7a79  mov     eax, 14h; jumptable 00000003839B7A1E case 20
0x3839b7a7e  mov     [r8], ax
0x3839b7a82  mov     rax, [rdx+10h]
0x3839b7a86  mov     [r8+8], rax
0x3839b7a8a  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7a8f  mov     r9d, 4; jumptable 00000003839B7A1E case 4
0x3839b7a95  mov     [r8], r9w
0x3839b7a99  mov     eax, [rdx+10h]
0x3839b7a9c  mov     [r8+8], eax
0x3839b7aa0  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7aa5  mov     eax, 5; jumptable 00000003839B7A1E case 5
0x3839b7aaa  mov     [r8], ax
0x3839b7aae  mov     rax, [rdx+10h]
0x3839b7ab2  mov     [r8+8], rax
0x3839b7ab6  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7abb  mov     eax, 6; jumptable 00000003839B7A1E cases 6,200
0x3839b7ac0  mov     [r8], ax
0x3839b7ac4  mov     rax, [rdx+10h]
0x3839b7ac8  mov     [r8+8], rax
0x3839b7acc  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7ad1  mov     eax, 0Bh; jumptable 00000003839B7A1E case 11
0x3839b7ad6  mov     [r8], ax
0x3839b7ada  movzx   eax, word ptr [rdx+10h]
0x3839b7ade  mov     [r8+8], ax
0x3839b7ae3  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7ae8  mov     eax, 7; jumptable 00000003839B7A1E cases 135,206
0x3839b7aed  lea     rcx, [rdx+10h]; struct tagDBTIMESTAMP *
0x3839b7af1  xor     r9d, r9d; bool
0x3839b7af4  mov     [r8], ax
0x3839b7af8  lea     r8, [rsp+2D8h+var_250]; void *
0x3839b7b00  lea     edx, [rax+1]; unsigned __int64
0x3839b7b03  call    ?DateTimeFromTimestamp@@YAGPEAUtagDBTIMESTAMP@@_KPEAX_N@Z; DateTimeFromTimestamp(tagDBTIMESTAMP *,unsigned __int64,void *,bool)
0x3839b7b08  test    ax, ax
0x3839b7b0b  jz      short loc_3839B7B57
0x3839b7b0d  test    byte ptr cs:_bidGblFlags, 2
0x3839b7b14  mov     ebx, 80004005h
0x3839b7b19  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7b1f  mov     rcx, cs:off_383B43258; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839b7b26  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7b2d  test    rax, rax
0x3839b7b30  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7b36  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7b3d  mov     r9d, ebx
0x3839b7b40  mov     edx, 6C3429h
0x3839b7b45  mov     dword ptr [rsp+2D8h+lpWideCharStr], 1B0Dh
0x3839b7b4d  call    _bidTraceW
0x3839b7b52  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7b57  mov     eax, [rsp+2D8h+var_24C]
0x3839b7b5e  xorps   xmm1, xmm1
0x3839b7b61  cvtsi2sd xmm1, rax
0x3839b7b66  mov     eax, [rsp+2D8h+var_250]
0x3839b7b6d  add     eax, 2
0x3839b7b70  movd    xmm0, eax
0x3839b7b74  divsd   xmm1, cs:__real@4178b82000000000
0x3839b7b7c  cvtdq2pd xmm0, xmm0
0x3839b7b80  comisd  xmm0, cs:__real@0000000000000000
0x3839b7b88  jb      short loc_3839B7B98
0x3839b7b8a  addsd   xmm0, xmm1
0x3839b7b8e  movsd   qword ptr [rdi+8], xmm0
0x3839b7b93  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7b98  subsd   xmm0, xmm1
0x3839b7b9c  movsd   qword ptr [rdi+8], xmm0
0x3839b7ba1  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7ba6  mov     eax, 8; jumptable 00000003839B7A1E cases 201,202
0x3839b7bab  mov     [r8], ax
0x3839b7baf  movsx   rdx, word ptr [rdx+10h]
0x3839b7bb4  mov     rcx, [rsi+18h]; strIn
0x3839b7bb8  shr     rdx, 1; ui
0x3839b7bbb  call    cs:__imp_SysAllocStringLen
0x3839b7bc1  mov     [rdi+8], rax
0x3839b7bc5  test    rax, rax
0x3839b7bc8  jnz     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7bce  test    byte ptr cs:_bidGblFlags, 2
0x3839b7bd5  mov     ebx, 8007000Eh
0x3839b7bda  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7be0  mov     rcx, cs:off_383B43258; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839b7be7  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7bee  test    rax, rax
0x3839b7bf1  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7bf7  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7bfe  mov     r9d, ebx
0x3839b7c01  mov     edx, 6C9C29h
0x3839b7c06  mov     dword ptr [rsp+2D8h+lpWideCharStr], 1B27h
0x3839b7c0e  call    _bidTraceW
0x3839b7c13  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7c18  lea     rcx, [rdx+20h]; jumptable 00000003839B7A1E cases 203,204
0x3839b7c1c  lea     rdx, [rsp+2D8h+CodePage]
0x3839b7c24  mov     [rsp+2D8h+CodePage], ebp
0x3839b7c2b  call    CodePageFromTDSCollation
0x3839b7c30  mov     ebx, eax
0x3839b7c32  test    eax, eax
0x3839b7c34  jns     short loc_3839B7C5C
0x3839b7c36  test    byte ptr cs:_bidGblFlags, 2
0x3839b7c3d  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7c43  mov     rcx, cs:off_383B43258; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839b7c4a  mov     r8d, eax
0x3839b7c4d  mov     edx, 6CE009h
0x3839b7c52  call    _bidTraceHR
0x3839b7c57  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7c5c  mov     ecx, [rsp+2D8h+CodePage]; CodePage
0x3839b7c63  mov     eax, 8
0x3839b7c68  xor     edx, edx; dwFlags
0x3839b7c6a  mov     [rdi], ax
0x3839b7c6d  movsx   r9d, word ptr [rsi+10h]; cbMultiByte
0x3839b7c72  mov     r8, [rsi+18h]; lpMultiByteStr
0x3839b7c76  mov     [rsp+2D8h+cchWideChar], ebp; cchWideChar
0x3839b7c7a  mov     [rsp+2D8h+lpWideCharStr], rbp; lpWideCharStr
0x3839b7c7f  call    cs:__imp_MultiByteToWideChar
0x3839b7c85  mov     ebp, eax
0x3839b7c87  test    eax, eax
0x3839b7c89  jnz     short loc_3839B7CD5
0x3839b7c8b  test    byte ptr cs:_bidGblFlags, 2
0x3839b7c92  mov     ebx, 80004005h
0x3839b7c97  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7c9d  mov     rcx, cs:off_383B43258; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839b7ca4  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7cab  test    rax, rax
0x3839b7cae  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7cb4  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7cbb  mov     r9d, ebx
0x3839b7cbe  mov     edx, 6D1829h
0x3839b7cc3  mov     dword ptr [rsp+2D8h+lpWideCharStr], 1B46h
0x3839b7ccb  call    _bidTraceW
0x3839b7cd0  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7cd5  mov     edx, eax; ui
0x3839b7cd7  xor     ecx, ecx; strIn
0x3839b7cd9  call    cs:__imp_SysAllocStringLen
0x3839b7cdf  mov     [rdi+8], rax
0x3839b7ce3  test    rax, rax
0x3839b7ce6  jnz     short loc_3839B7D32
0x3839b7ce8  test    byte ptr cs:_bidGblFlags, 2
0x3839b7cef  mov     ebx, 8007000Eh
0x3839b7cf4  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7cfa  mov     rcx, cs:off_383B43258; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839b7d01  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7d08  test    rax, rax
0x3839b7d0b  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7d11  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7d18  mov     r9d, ebx
0x3839b7d1b  mov     edx, 6D3829h
0x3839b7d20  mov     dword ptr [rsp+2D8h+lpWideCharStr], 1B4Eh
0x3839b7d28  call    _bidTraceW
0x3839b7d2d  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7d32  movsx   r9d, word ptr [rsi+10h]; cbMultiByte
0x3839b7d37  mov     r8, [rsi+18h]; lpMultiByteStr
0x3839b7d3b  mov     ecx, [rsp+2D8h+CodePage]; CodePage
0x3839b7d42  xor     edx, edx; dwFlags
0x3839b7d44  mov     [rsp+2D8h+cchWideChar], ebp; cchWideChar
0x3839b7d48  mov     [rsp+2D8h+lpWideCharStr], rax; lpWideCharStr
0x3839b7d4d  call    cs:__imp_MultiByteToWideChar
0x3839b7d53  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7d58  mov     eax, 2011h; jumptable 00000003839B7A1E cases 207,208
0x3839b7d5d  mov     ecx, 11h; vt
0x3839b7d62  mov     [r8], ax
0x3839b7d66  movsx   r8d, word ptr [rdx+10h]; cElements
0x3839b7d6b  xor     edx, edx; lLbound
0x3839b7d6d  call    cs:__imp_SafeArrayCreateVector
0x3839b7d73  mov     [rdi+8], rax
0x3839b7d77  test    rax, rax
0x3839b7d7a  jnz     short loc_3839B7DC6
0x3839b7d7c  test    byte ptr cs:_bidGblFlags, 2
0x3839b7d83  mov     ebx, 8007000Eh
0x3839b7d88  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7d8e  mov     rcx, cs:off_383B43258; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839b7d95  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7d9c  test    rax, rax
0x3839b7d9f  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7da5  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7dac  mov     r9d, ebx
0x3839b7daf  mov     edx, 6DA429h
0x3839b7db4  mov     dword ptr [rsp+2D8h+lpWideCharStr], 1B69h
0x3839b7dbc  call    _bidTraceW
0x3839b7dc1  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7dc6  lea     rdx, [rsp+2D8h+ppvData]; ppvData
0x3839b7dce  mov     rcx, rax; psa
0x3839b7dd1  mov     [rsp+2D8h+ppvData], rbp
0x3839b7dd9  call    cs:__imp_SafeArrayAccessData
0x3839b7ddf  test    eax, eax
0x3839b7de1  jns     short loc_3839B7E2D
0x3839b7de3  test    byte ptr cs:_bidGblFlags, 2
0x3839b7dea  mov     ebx, 80004005h
0x3839b7def  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7df5  mov     rcx, cs:off_383B43258; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839b7dfc  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7e03  test    rax, rax
0x3839b7e06  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7e0c  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7e13  mov     r9d, ebx
0x3839b7e16  mov     edx, 6DC429h
0x3839b7e1b  mov     dword ptr [rsp+2D8h+lpWideCharStr], 1B71h
0x3839b7e23  call    _bidTraceW
0x3839b7e28  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7e2d  movsx   r8, word ptr [rsi+10h]; Size
0x3839b7e32  mov     rdx, [rsi+18h]; Src
0x3839b7e36  mov     rcx, [rsp+2D8h+ppvData]; void *
0x3839b7e3e  call    memcpy
0x3839b7e43  mov     rcx, [rdi+8]; psa
0x3839b7e47  call    cs:__imp_SafeArrayUnaccessData
0x3839b7e4d  mov     ebx, eax
0x3839b7e4f  test    eax, eax
0x3839b7e51  jns     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7e57  test    byte ptr cs:_bidGblFlags, 2
0x3839b7e5e  mov     ebx, 80004005h
0x3839b7e63  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7e69  mov     rcx, cs:off_383B43258; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839b7e70  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7e77  test    rax, rax
0x3839b7e7a  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7e80  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7e87  mov     r9d, ebx
0x3839b7e8a  mov     edx, 6DF029h
0x3839b7e8f  mov     dword ptr [rsp+2D8h+lpWideCharStr], 1B7Ch
0x3839b7e97  call    _bidTraceW
0x3839b7e9c  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7ea1  mov     eax, 0Eh; jumptable 00000003839B7A1E cases 131,205
0x3839b7ea6  lea     rcx, [rdx+10h]; struct tagDB_NUMERIC *
0x3839b7eaa  lea     rdx, [rsp+2D8h+strIn]; unsigned __int16 *
0x3839b7eb2  mov     [r8], ax
0x3839b7eb6  lea     r8, [rsp+2D8h+var_240]; unsigned __int64 *
0x3839b7ebe  mov     [rsp+2D8h+var_240], rbp
0x3839b7ec6  call    ?_VarStrFromNum@@YAJPEBUtagDB_NUMERIC@@PEAGPEA_K_K@Z; _VarStrFromNum(tagDB_NUMERIC const *,ushort *,unsigned __int64 *,unsigned __int64)
0x3839b7ecb  test    eax, eax
0x3839b7ecd  jns     short loc_3839B7F19
0x3839b7ecf  test    byte ptr cs:_bidGblFlags, 2
0x3839b7ed6  mov     ebx, 80004005h
0x3839b7edb  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7ee1  mov     rcx, cs:off_383B43258; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839b7ee8  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7eef  test    rax, rax
0x3839b7ef2  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7ef8  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7eff  mov     r9d, ebx
0x3839b7f02  mov     edx, 6E3029h
0x3839b7f07  mov     dword ptr [rsp+2D8h+lpWideCharStr], 1B8Ch
0x3839b7f0f  call    _bidTraceW
0x3839b7f14  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7f19  lea     rcx, [rsp+2D8h+strIn]; strIn
0x3839b7f21  mov     r9, rdi; pdecOut
0x3839b7f24  xor     r8d, r8d; dwFlags
0x3839b7f27  mov     edx, 409h; lcid
0x3839b7f2c  call    cs:__imp_VarDecFromStr
0x3839b7f32  mov     ebx, eax
0x3839b7f34  test    eax, eax
0x3839b7f36  jns     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7f3c  test    byte ptr cs:_bidGblFlags, 2
0x3839b7f43  mov     ebx, 80004005h
0x3839b7f48  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7f4e  mov     rcx, cs:off_383B43258; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839b7f55  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7f5c  test    rax, rax
0x3839b7f5f  jz      def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7f65  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839b7f6c  mov     r9d, ebx
0x3839b7f6f  mov     edx, 6E4829h
0x3839b7f74  mov     dword ptr [rsp+2D8h+lpWideCharStr], 1B92h
0x3839b7f7c  call    _bidTraceW
0x3839b7f81  jmp     def_3839B7A1E; jumptable 00000003839B7A1E default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x3839b7f86  mov     [rsp+2D8h+var_260], ebp; jumptable 00000003839B7A1E case 133
  ... truncated ...
```
