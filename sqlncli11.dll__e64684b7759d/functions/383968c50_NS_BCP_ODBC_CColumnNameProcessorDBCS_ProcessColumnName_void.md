# NS_BCP_ODBC::CColumnNameProcessorDBCS::ProcessColumnName(void)

- ea: `0x383968c50`
- end: `0x383968e69`
- name: `?ProcessColumnName@CColumnNameProcessorDBCS@NS_BCP_ODBC@@UEAAFXZ`
- size: `537`
- prototype: `__int16 __fastcall(NS_BCP_ODBC::CColumnNameProcessorDBCS *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x38391aed0`
- `0x383968c50`
- `0x383976a90`
- `0x383a9ee60`

## import_xrefs

- `MSVCR100!iswspace` at `0x383968cef`
- `MSVCR100!iswspace` at `0x383968cef`
- `KERNEL32!IsDBCSLeadByteEx` at `0x383968c9e`
- `KERNEL32!IsDBCSLeadByteEx` at `0x383968c9e`
- `KERNEL32!SetFilePointer` at `0x383968d64`
- `KERNEL32!SetFilePointer` at `0x383968d64`

## pseudocode

```c
__int64 __fastcall NS_BCP_ODBC::CColumnNameProcessorDBCS::ProcessColumnName(
        NS_BCP_ODBC::CColumnNameProcessorDBCS *this)
{
  __int16 v1; // di
  int v3; // esi
  char *v4; // rcx
  __int64 v5; // r9
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rdx

  v1 = 0;
  *((_DWORD *)this + 3) = 0;
  while ( 1 )
  {
    if ( (unsigned __int16)bcpRead(
                             *((struct tagDBC **)this + 2),
                             *((struct BCPFILE **)this + 3),
                             1u,
                             (unsigned __int8 *)this + 40) )
    {
      v1 = -1;
      if ( (bidGblFlags & 2) != 0 )
      {
        v4 = off_383B43238[0];
        if ( off_383B49120[0] )
        {
          v5 = 1149;
          v6 = 1176585;
          goto LABEL_27;
        }
      }
      goto LABEL_28;
    }
    v3 = 1;
    if ( IsDBCSLeadByteEx(*((_DWORD *)this + 8), *((_BYTE *)this + 40)) )
      break;
LABEL_6:
    if ( !FastMultiByteToWideChar(*((_DWORD *)this + 8), (LPCCH)this + 40, v3, (LPWSTR)this + 4, 1) )
    {
      v1 = -1;
      if ( (bidGblFlags & 2) != 0 )
      {
        v4 = off_383B43238[0];
        if ( off_383B49120[0] )
        {
          v5 = 1168;
          v6 = 1196041;
          goto LABEL_27;
        }
      }
      goto LABEL_28;
    }
    if ( iswspace(*((_WORD *)this + 4)) )
    {
      v7 = *((_QWORD *)this + 3);
      if ( *(_DWORD *)(v7 + 64) )
        *(_QWORD *)(v7 + 56) -= v3;
      else
        SetFilePointer(*(HANDLE *)v7, -v3, 0, 1u);
LABEL_16:
      v8 = *((_DWORD *)this + 3);
      if ( !v8 || v8 > 129 )
      {
        v1 = -1;
        if ( (bidGblFlags & 2) != 0 )
        {
          v4 = off_383B43238[0];
          if ( off_383B49120[0] )
          {
            v5 = 1184;
            v6 = 1212425;
            goto LABEL_27;
          }
        }
      }
      goto LABEL_28;
    }
    if ( (int)++*((_DWORD *)this + 3) > 129 )
      goto LABEL_16;
  }
  if ( !(unsigned __int16)bcpRead(
                            *((struct tagDBC **)this + 2),
                            *((struct BCPFILE **)this + 3),
                            1u,
                            (unsigned __int8 *)this + 41) )
  {
    v3 = 2;
    goto LABEL_6;
  }
  v1 = -1;
  if ( (bidGblFlags & 2) != 0 )
  {
    v4 = off_383B43238[0];
    if ( off_383B49120[0] )
    {
      v5 = 1156;
      v6 = 1183753;
LABEL_27:
      bidTraceW(v4, v6, off_383B49120[0], v5);
    }
  }
LABEL_28:
  if ( (bidGblFlags & 2) != 0 && (v1 || (bidGblFlags & 0x40) != 0) )
  {
    v9 = 1215489;
    if ( v1 )
      v9 = 1215521;
    bidTraceW(off_383B43238[0], v9, off_383B494E8[0], (unsigned int)v1);
  }
  return (unsigned __int16)v1;
}

```

## disassembly

```asm
0x383968c50  push    rdi
0x383968c52  sub     rsp, 30h
0x383968c56  mov     [rsp+38h+arg_0], rbx
0x383968c5b  mov     [rsp+38h+arg_18], r15
0x383968c60  xor     edi, edi
0x383968c62  mov     [rsp+38h+arg_8], rsi
0x383968c67  mov     rbx, rcx
0x383968c6a  mov     [rcx+0Ch], edi
0x383968c6d  mov     [rsp+38h+arg_10], r14
0x383968c72  mov     rdx, [rbx+18h]; struct BCPFILE *
0x383968c76  mov     rcx, [rbx+10h]; struct tagDBC *
0x383968c7a  lea     r9, [rbx+28h]; unsigned __int8 *
0x383968c7e  mov     r8d, 1; unsigned int
0x383968c84  call    ?bcpRead@@YAFPEAUtagDBC@@PEAUBCPFILE@@IPEAE@Z; bcpRead(tagDBC *,BCPFILE *,uint,uchar *)
0x383968c89  cmp     di, ax
0x383968c8c  jnz     loc_383968DD8
0x383968c92  movzx   edx, byte ptr [rbx+28h]; TestChar
0x383968c96  mov     ecx, [rbx+20h]; CodePage
0x383968c99  mov     esi, 1
0x383968c9e  call    cs:__imp_IsDBCSLeadByteEx
0x383968ca4  test    eax, eax
0x383968ca6  jz      short loc_383968CC6
0x383968ca8  mov     rdx, [rbx+18h]; struct BCPFILE *
0x383968cac  mov     rcx, [rbx+10h]; struct tagDBC *
0x383968cb0  lea     r9, [rbx+29h]; unsigned __int8 *
0x383968cb4  mov     r8d, esi; unsigned int
0x383968cb7  call    ?bcpRead@@YAFPEAUtagDBC@@PEAUBCPFILE@@IPEAE@Z; bcpRead(tagDBC *,BCPFILE *,uint,uchar *)
0x383968cbc  cmp     di, ax
0x383968cbf  jnz     short loc_383968D0B
0x383968cc1  mov     esi, 2
0x383968cc6  mov     ecx, [rbx+20h]; CodePage
0x383968cc9  lea     r9, [rbx+8]; lpWideCharStr
0x383968ccd  lea     rdx, [rbx+28h]; lpMultiByteStr
0x383968cd1  movsxd  r8, esi; cbMultiByte
0x383968cd4  mov     [rsp+38h+var_18], 1; __int64
0x383968cdd  call    ?FastMultiByteToWideChar@@YA_JIPEBD_JPEAG1@Z; FastMultiByteToWideChar(uint,char const *,__int64,ushort *,__int64)
0x383968ce2  test    rax, rax
0x383968ce5  jz      loc_383968DAC
0x383968ceb  movzx   ecx, word ptr [rbx+8]; C
0x383968cef  call    cs:__imp_iswspace
0x383968cf5  test    eax, eax
0x383968cf7  jnz     short loc_383968D42
0x383968cf9  inc     dword ptr [rbx+0Ch]
0x383968cfc  cmp     dword ptr [rbx+0Ch], 81h
0x383968d03  jle     loc_383968C72
0x383968d09  jmp     short loc_383968D6A
0x383968d0b  or      edi, 0FFFFFFFFh
0x383968d0e  test    byte ptr cs:_bidGblFlags, 2
0x383968d15  jz      loc_383968E0E
0x383968d1b  mov     rcx, cs:off_383B43238; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383968d22  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383968d29  test    rax, rax
0x383968d2c  jz      loc_383968E0E
0x383968d32  mov     r9d, 484h
0x383968d38  mov     edx, 121009h
0x383968d3d  jmp     loc_383968E02
0x383968d42  mov     rcx, [rbx+18h]
0x383968d46  cmp     [rcx+40h], edi
0x383968d49  jz      short loc_383968D54
0x383968d4b  movsxd  rax, esi
0x383968d4e  sub     [rcx+38h], rax
0x383968d52  jmp     short loc_383968D6A
0x383968d54  mov     rcx, [rcx]; hFile
0x383968d57  neg     esi
0x383968d59  mov     r9d, 1; dwMoveMethod
0x383968d5f  mov     edx, esi; lDistanceToMove
0x383968d61  xor     r8d, r8d; lpDistanceToMoveHigh
0x383968d64  call    cs:__imp_SetFilePointer
0x383968d6a  mov     eax, [rbx+0Ch]
0x383968d6d  test    eax, eax
0x383968d6f  jz      short loc_383968D7C
0x383968d71  cmp     eax, 81h
0x383968d76  jle     loc_383968E0E
0x383968d7c  or      edi, 0FFFFFFFFh
0x383968d7f  test    byte ptr cs:_bidGblFlags, 2
0x383968d86  jz      loc_383968E0E
0x383968d8c  mov     rcx, cs:off_383B43238; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383968d93  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383968d9a  test    rax, rax
0x383968d9d  jz      short loc_383968E0E
0x383968d9f  mov     r9d, 4A0h
0x383968da5  mov     edx, 128009h
0x383968daa  jmp     short loc_383968E02
0x383968dac  or      edi, 0FFFFFFFFh
0x383968daf  test    byte ptr cs:_bidGblFlags, 2
0x383968db6  jz      short loc_383968E0E
0x383968db8  mov     rcx, cs:off_383B43238; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383968dbf  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383968dc6  test    rax, rax
0x383968dc9  jz      short loc_383968E0E
0x383968dcb  mov     r9d, 490h
0x383968dd1  mov     edx, 124009h
0x383968dd6  jmp     short loc_383968E02
0x383968dd8  or      edi, 0FFFFFFFFh
0x383968ddb  test    byte ptr cs:_bidGblFlags, 2
0x383968de2  jz      short loc_383968E0E
0x383968de4  mov     rcx, cs:off_383B43238; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383968deb  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383968df2  test    rax, rax
0x383968df5  jz      short loc_383968E0E
0x383968df7  mov     r9d, 47Dh
0x383968dfd  mov     edx, 11F409h
0x383968e02  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x383968e09  call    _bidTraceW
0x383968e0e  test    byte ptr cs:_bidGblFlags, 2
0x383968e15  mov     r15, [rsp+38h+arg_18]
0x383968e1a  mov     r14, [rsp+38h+arg_10]
0x383968e1f  mov     rsi, [rsp+38h+arg_8]
0x383968e24  mov     rbx, [rsp+38h+arg_0]
0x383968e29  jz      short loc_383968E60
0x383968e2b  mov     rcx, cs:off_383B43238; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383968e32  mov     r8, cs:off_383B494E8; "<ODBC|DRIVER|RET> %d{SQLRETURN}\n"
0x383968e39  test    di, di
0x383968e3c  jnz     short loc_383968E47
0x383968e3e  test    byte ptr cs:_bidGblFlags, 40h
0x383968e45  jz      short loc_383968E60
0x383968e47  mov     eax, 128C21h
0x383968e4c  test    di, di
0x383968e4f  mov     edx, 128C01h
0x383968e54  cmovnz  edx, eax
0x383968e57  movsx   r9d, di
0x383968e5b  call    _bidTraceW
0x383968e60  movzx   eax, di
0x383968e63  add     rsp, 30h
0x383968e67  pop     rdi
0x383968e68  retn
```
