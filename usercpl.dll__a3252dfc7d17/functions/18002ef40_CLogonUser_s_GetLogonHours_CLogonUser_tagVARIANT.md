# CLogonUser::s_GetLogonHours(CLogonUser *,tagVARIANT *)

- ea: `0x18002ef40`
- end: `0x18002f05d`
- name: `?s_GetLogonHours@CLogonUser@@CAJPEAV1@PEAUtagVARIANT@@@Z`
- size: `285`
- prototype: `static int(struct CLogonUser *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002ef40`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002ef53`
- `OLEAUT32!__imp_VariantInit` at `0x18002ef53`
- `OLEAUT32!__imp_VariantClear` at `0x18002f04a`
- `OLEAUT32!__imp_VariantClear` at `0x18002f04a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002efb8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002efb8`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002f01c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002f01c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002ef8f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002ef8f`
- `samcli!NetUserGetInfo` at `0x18002ef71`
- `samcli!NetUserGetInfo` at `0x18002ef71`
- `netutils!NetApiBufferFree` at `0x18002f030`
- `netutils!NetApiBufferFree` at `0x18002f030`

## pseudocode

```c
__int64 __fastcall CLogonUser::s_GetLogonHours(const WCHAR *a1, struct tagVARIANT *a2)
{
  signed int Info; // eax
  int v5; // ebx
  SAFEARRAY *Vector; // rax
  LPBYTE v7; // rax
  __int64 i; // r8
  __int64 v9; // r9
  LPBYTE bufptr; // [rsp+30h] [rbp+8h] BYREF
  void *ppvData; // [rsp+40h] [rbp+18h] BYREF

  VariantInit(a2);
  bufptr = 0;
  Info = NetUserGetInfo(0, a1 + 6, 2u, &bufptr);
  v5 = Info;
  if ( Info )
  {
    if ( Info > 0 )
      v5 = (unsigned __int16)Info | 0x80070000;
  }
  else
  {
    Vector = SafeArrayCreateVector(0xBu, 0, *((_DWORD *)bufptr + 28));
    a2->llVal = (LONGLONG)Vector;
    if ( Vector )
    {
      a2->vt = 8203;
      ppvData = 0;
      v5 = SafeArrayAccessData(Vector, &ppvData);
      if ( v5 >= 0 )
      {
        v7 = bufptr;
        for ( i = 0; (unsigned int)i < *((_DWORD *)bufptr + 28); i = (unsigned int)(i + 1) )
        {
          v9 = 2 * i;
          if ( (*(_BYTE *)(((unsigned __int64)(unsigned int)i >> 3) + *((_QWORD *)v7 + 15))
              & (unsigned __int8)(1 << (i & 7))) != 0 )
            *(_WORD *)((char *)ppvData + v9) = -1;
          else
            *(_WORD *)((char *)ppvData + v9) = 0;
          v7 = bufptr;
        }
        SafeArrayUnaccessData(a2->parray);
        v5 = 0;
      }
    }
    else
    {
      v5 = -2147024882;
    }
    NetApiBufferFree(bufptr);
  }
  if ( v5 < 0 )
    VariantClear(a2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002ef40  mov     [rsp+arg_8], rbx
0x18002ef45  push    rdi
0x18002ef46  sub     rsp, 20h
0x18002ef4a  mov     rbx, rcx
0x18002ef4d  mov     rdi, rdx
0x18002ef50  mov     rcx, rdx; pvarg
0x18002ef53  call    cs:__imp_VariantInit
0x18002ef59  xor     ecx, ecx; servername
0x18002ef5b  mov     [rsp+28h+bufptr], 0
0x18002ef64  lea     rdx, [rbx+0Ch]; username
0x18002ef68  lea     r9, [rsp+28h+bufptr]; bufptr
0x18002ef6d  lea     r8d, [rcx+2]; level
0x18002ef71  call    cs:__imp_NetUserGetInfo
0x18002ef77  mov     ebx, eax
0x18002ef79  test    eax, eax
0x18002ef7b  jnz     loc_18002F038
0x18002ef81  mov     r8, [rsp+28h+bufptr]
0x18002ef86  lea     ecx, [rax+0Bh]; vt
0x18002ef89  xor     edx, edx; lLbound
0x18002ef8b  mov     r8d, [r8+70h]; cElements
0x18002ef8f  call    cs:__imp_SafeArrayCreateVector
0x18002ef95  mov     [rdi+8], rax
0x18002ef99  test    rax, rax
0x18002ef9c  jz      loc_18002F026
0x18002efa2  lea     rdx, [rsp+28h+ppvData]; ppvData
0x18002efa7  mov     word ptr [rdi], 200Bh
0x18002efac  mov     rcx, rax; psa
0x18002efaf  mov     [rsp+28h+ppvData], 0
0x18002efb8  call    cs:__imp_SafeArrayAccessData
0x18002efbe  mov     ebx, eax
0x18002efc0  test    eax, eax
0x18002efc2  js      short loc_18002F02B
0x18002efc4  mov     rax, [rsp+28h+bufptr]
0x18002efc9  xor     r8d, r8d
0x18002efcc  cmp     [rax+70h], r8d
0x18002efd0  jbe     short loc_18002F018
0x18002efd2  mov     rax, [rax+78h]
0x18002efd6  lea     r9, [r8+r8]
0x18002efda  mov     ecx, r8d
0x18002efdd  shr     rcx, 3
0x18002efe1  mov     dl, [rcx+rax]
0x18002efe4  mov     eax, 1
0x18002efe9  mov     ecx, r8d
0x18002efec  and     ecx, 7
0x18002efef  shl     eax, cl
0x18002eff1  test    al, dl
0x18002eff3  mov     rax, [rsp+28h+ppvData]
0x18002eff8  jz      short loc_18002F003
0x18002effa  mov     word ptr [r9+rax], 0FFFFh
0x18002f001  jmp     short loc_18002F00A
0x18002f003  xor     ecx, ecx
0x18002f005  mov     [r9+rax], cx
0x18002f00a  mov     rax, [rsp+28h+bufptr]
0x18002f00f  inc     r8d
0x18002f012  cmp     r8d, [rax+70h]
0x18002f016  jb      short loc_18002EFD2
0x18002f018  mov     rcx, [rdi+8]; psa
0x18002f01c  call    cs:__imp_SafeArrayUnaccessData
0x18002f022  xor     ebx, ebx
0x18002f024  jmp     short loc_18002F02B
0x18002f026  mov     ebx, 8007000Eh
0x18002f02b  mov     rcx, [rsp+28h+bufptr]; Buffer
0x18002f030  call    cs:__imp_NetApiBufferFree
0x18002f036  jmp     short loc_18002F043
0x18002f038  jle     short loc_18002F043
0x18002f03a  movzx   ebx, ax
0x18002f03d  or      ebx, 80070000h
0x18002f043  test    ebx, ebx
0x18002f045  jns     short loc_18002F050
0x18002f047  mov     rcx, rdi; pvarg
0x18002f04a  call    cs:__imp_VariantClear
0x18002f050  mov     eax, ebx
0x18002f052  mov     rbx, [rsp+28h+arg_8]
0x18002f057  add     rsp, 20h
0x18002f05b  pop     rdi
0x18002f05c  retn
```
