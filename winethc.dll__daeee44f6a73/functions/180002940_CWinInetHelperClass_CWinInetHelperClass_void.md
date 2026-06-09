# CWinInetHelperClass::CWinInetHelperClass(void)

- ea: `0x180002940`
- end: `0x180002ba0`
- name: `??0CWinInetHelperClass@@QEAA@XZ`
- size: `608`
- prototype: `CWinInetHelperClass *__fastcall(CWinInetHelperClass *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000448c`

## callees

- `0x180002940`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002a0f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002a0f`

## pseudocode

```c
CWinInetHelperClass *__fastcall CWinInetHelperClass::CWinInetHelperClass(CWinInetHelperClass *this)
{
  __int64 v2; // rdi
  char *v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rdx
  char *v7; // rax
  char *v8; // rax
  __int64 v9; // rcx
  char *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  char *v13; // rax
  char *v14; // rax
  __int64 v15; // rdx
  char *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  char *v19; // rax
  char *v20; // rax
  __int64 v21; // rcx
  char *v22; // rax
  char *v23; // rax
  __int64 v24; // rcx
  char *v25; // rax
  CWinInetHelperClass *result; // rax

  *((_DWORD *)this + 16) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  v2 = 128;
  *(_OWORD *)((char *)this + 88) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_BYTE *)this + 112) = 0;
  *(_QWORD *)this = &CNetDiagHelperImpl::`vftable'{for `INetDiagHelper'};
  *((_QWORD *)this + 1) = &CNetDiagHelperImpl::`vftable'{for `INetDiagHelperInfo'};
  *((_QWORD *)this + 7) = &CNetDiagHelperExImpl::`vftable';
  v3 = (char *)this + 2888;
  *(_QWORD *)((char *)this + 20) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 640) = 0;
  v4 = 128;
  do
  {
    *v3++ = 0;
    --v4;
  }
  while ( v4 );
  *((_WORD *)this + 572) = 0;
  *((_QWORD *)this + 602) = 0;
  *((_WORD *)this + 60) = 0;
  *((_WORD *)this + 316) = 0;
  *((_DWORD *)this + 287) = 0;
  *((_WORD *)this + 1174) = 0;
  *((_DWORD *)this + 718) = 0;
  *((_QWORD *)this + 360) = 0;
  *((_QWORD *)this + 377) = 0;
  *((_DWORD *)this + 1202) = 1;
  CoCreateInstance(&CLSID_NDFEtw, 0, 1u, &IID_INDFEtw, (LPVOID *)this + 602);
  v5 = 598;
  *((_QWORD *)this + 603) = 0;
  v6 = 598;
  v7 = (char *)this + 1152;
  do
  {
    *v7++ = 0;
    --v6;
  }
  while ( v6 );
  v8 = (char *)this + 1750;
  do
  {
    *v8++ = 0;
    --v5;
  }
  while ( v5 );
  v9 = 32;
  v10 = (char *)this + 4424;
  v11 = 32;
  do
  {
    *v10++ = 0;
    --v11;
  }
  while ( v11 );
  v12 = 352;
  v13 = (char *)this + 4456;
  do
  {
    *v13++ = 0;
    --v12;
  }
  while ( v12 );
  *((_DWORD *)this + 1203) = 0;
  v14 = (char *)this + 4832;
  v15 = 16;
  do
  {
    *v14++ = 0;
    --v15;
  }
  while ( v15 );
  *((_DWORD *)this + 1212) = 0;
  v16 = (char *)this + 4856;
  v17 = 32;
  do
  {
    *v16++ = 0;
    --v17;
  }
  while ( v17 );
  v18 = 24;
  v19 = (char *)this + 4896;
  do
  {
    *v19++ = 0;
    --v18;
  }
  while ( v18 );
  v20 = (char *)this + 4920;
  do
  {
    *v20++ = 0;
    --v9;
  }
  while ( v9 );
  v21 = 128;
  v22 = (char *)this + 3024;
  do
  {
    *v22++ = 0;
    --v21;
  }
  while ( v21 );
  *((_DWORD *)this + 788) = 0;
  v23 = (char *)this + 4968;
  *((_QWORD *)this + 619) = 0;
  v24 = 128;
  *((_DWORD *)this + 1240) = 0;
  do
  {
    *v23++ = 0;
    --v24;
  }
  while ( v24 );
  *((_DWORD *)this + 1222) = 0;
  v25 = (char *)this + 4288;
  *((_DWORD *)this + 790) = 1;
  *((_DWORD *)this + 789) = 0;
  *((_DWORD *)this + 791) = 0;
  *((_DWORD *)this + 792) = 1;
  *((_DWORD *)this + 793) = 1;
  *((_WORD *)this + 2208) = 80;
  *((_WORD *)this + 1588) = 0;
  *((_WORD *)this + 1844) = 0;
  do
  {
    *v25++ = 0;
    --v2;
  }
  while ( v2 );
  *((_QWORD *)this + 637) = 1;
  result = this;
  *((_DWORD *)this + 1276) = 0;
  *((_DWORD *)this + 1277) = 2;
  *((_QWORD *)this + 639) = 0;
  *((_QWORD *)this + 640) = 0;
  *((_DWORD *)this + 1105) = 0;
  return result;
}

```

## disassembly

```asm
0x180002940  push    rbx
0x180002942  push    rbp
0x180002943  push    rsi
0x180002944  push    rdi
0x180002945  sub     rsp, 38h
0x180002949  xor     esi, esi
0x18000294b  xorps   xmm0, xmm0
0x18000294e  mov     [rcx+40h], esi
0x180002951  xor     eax, eax
0x180002953  movups  xmmword ptr [rcx+48h], xmm0
0x180002957  mov     rbx, rcx
0x18000295a  mov     edi, 80h
0x18000295f  movups  xmmword ptr [rcx+58h], xmm0
0x180002963  mov     [rcx+68h], rax
0x180002967  lea     ebp, [rsi+1]
0x18000296a  mov     [rcx+70h], sil
0x18000296e  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelper@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelper'}
0x180002975  mov     [rcx], rax
0x180002978  lea     rax, ??_7CNetDiagHelperImpl@@6BINetDiagHelperInfo@@@; const CNetDiagHelperImpl::`vftable'{for `INetDiagHelperInfo'}
0x18000297f  mov     [rcx+8], rax
0x180002983  lea     rax, ??_7CNetDiagHelperExImpl@@6B@; const CNetDiagHelperExImpl::`vftable'
0x18000298a  mov     [rcx+38h], rax
0x18000298e  lea     rax, [rbx+0B48h]
0x180002995  mov     [rcx+14h], rsi
0x180002999  mov     [rcx+20h], rsi
0x18000299d  mov     [rcx+10h], esi
0x1800029a0  mov     [rcx+1400h], rsi
0x1800029a7  mov     ecx, edi
0x1800029a9  mov     [rax], sil
0x1800029ac  add     rax, rbp
0x1800029af  sub     rcx, rbp
0x1800029b2  jnz     short loc_1800029A9
0x1800029b4  lea     rax, [rbx+12D0h]
0x1800029bb  mov     [rbx+478h], si
0x1800029c2  lea     r9, IID_INDFEtw; riid
0x1800029c9  mov     [rax], rsi
0x1800029cc  mov     r8d, ebp; dwClsContext
0x1800029cf  mov     [rsp+58h+ppv], rax; ppv
0x1800029d4  xor     edx, edx; pUnkOuter
0x1800029d6  mov     [rbx+78h], si
0x1800029da  lea     rcx, CLSID_NDFEtw; rclsid
0x1800029e1  mov     [rbx+278h], si
0x1800029e8  mov     [rbx+47Ch], esi
0x1800029ee  mov     [rbx+92Ch], si
0x1800029f5  mov     [rbx+0B38h], esi
0x1800029fb  mov     [rbx+0B40h], rsi
0x180002a02  mov     [rbx+0BC8h], rsi
0x180002a09  mov     [rbx+12C8h], ebp
0x180002a0f  call    cs:__imp_CoCreateInstance
0x180002a16  nop     dword ptr [rax+rax+00h]
0x180002a1b  mov     ecx, 256h
0x180002a20  mov     [rbx+12D8h], rsi
0x180002a27  mov     edx, ecx
0x180002a29  lea     rax, [rbx+480h]
0x180002a30  mov     [rax], sil
0x180002a33  add     rax, rbp
0x180002a36  sub     rdx, rbp
0x180002a39  jnz     short loc_180002A30
0x180002a3b  lea     rax, [rbx+6D6h]
0x180002a42  mov     [rax], sil
0x180002a45  add     rax, rbp
0x180002a48  sub     rcx, rbp
0x180002a4b  jnz     short loc_180002A42
0x180002a4d  mov     ecx, 20h ; ' '
0x180002a52  lea     rax, [rbx+1148h]
0x180002a59  mov     edx, ecx
0x180002a5b  mov     [rax], sil
0x180002a5e  add     rax, rbp
0x180002a61  sub     rdx, rbp
0x180002a64  jnz     short loc_180002A5B
0x180002a66  mov     edx, 160h
0x180002a6b  lea     rax, [rbx+1168h]
0x180002a72  mov     [rax], sil
0x180002a75  add     rax, rbp
0x180002a78  sub     rdx, rbp
0x180002a7b  jnz     short loc_180002A72
0x180002a7d  mov     [rbx+12CCh], esi
0x180002a83  lea     rax, [rbx+12E0h]
0x180002a8a  mov     edx, 10h
0x180002a8f  mov     [rax], sil
0x180002a92  add     rax, rbp
0x180002a95  sub     rdx, rbp
0x180002a98  jnz     short loc_180002A8F
0x180002a9a  mov     [rbx+12F0h], esi
0x180002aa0  lea     rax, [rbx+12F8h]
0x180002aa7  mov     rdx, rcx
0x180002aaa  mov     [rax], sil
0x180002aad  add     rax, rbp
0x180002ab0  sub     rdx, rbp
0x180002ab3  jnz     short loc_180002AAA
0x180002ab5  mov     edx, 18h
0x180002aba  lea     rax, [rbx+1320h]
0x180002ac1  mov     [rax], sil
0x180002ac4  add     rax, rbp
0x180002ac7  sub     rdx, rbp
0x180002aca  jnz     short loc_180002AC1
0x180002acc  lea     rax, [rbx+1338h]
0x180002ad3  mov     [rax], sil
0x180002ad6  add     rax, rbp
0x180002ad9  sub     rcx, rbp
0x180002adc  jnz     short loc_180002AD3
0x180002ade  mov     rcx, rdi
0x180002ae1  lea     rax, [rbx+0BD0h]
0x180002ae8  mov     [rax], sil
0x180002aeb  add     rax, rbp
0x180002aee  sub     rcx, rbp
0x180002af1  jnz     short loc_180002AE8
0x180002af3  mov     [rbx+0C50h], esi
0x180002af9  lea     rax, [rbx+1368h]
0x180002b00  mov     [rbx+1358h], rsi
0x180002b07  mov     rcx, rdi
0x180002b0a  mov     [rbx+1360h], esi
0x180002b10  mov     [rax], sil
0x180002b13  add     rax, rbp
0x180002b16  sub     rcx, rbp
0x180002b19  jnz     short loc_180002B10
0x180002b1b  mov     [rbx+1318h], esi
0x180002b21  lea     rax, [rbx+10C0h]
0x180002b28  mov     [rbx+0C58h], ebp
0x180002b2e  mov     [rbx+0C54h], esi
0x180002b34  mov     [rbx+0C5Ch], esi
0x180002b3a  mov     [rbx+0C60h], ebp
0x180002b40  mov     [rbx+0C64h], ebp
0x180002b46  mov     word ptr [rbx+1140h], 50h ; 'P'
0x180002b4f  mov     [rbx+0C68h], si
0x180002b56  mov     [rbx+0E68h], si
0x180002b5d  mov     [rax], sil
0x180002b60  add     rax, rbp
0x180002b63  sub     rdi, rbp
0x180002b66  jnz     short loc_180002B5D
0x180002b68  mov     [rbx+13E8h], rbp
0x180002b6f  mov     rax, rbx
0x180002b72  mov     [rbx+13F0h], esi
0x180002b78  mov     dword ptr [rbx+13F4h], 2
0x180002b82  mov     [rbx+13F8h], rsi
0x180002b89  mov     [rbx+1400h], rsi
0x180002b90  mov     [rbx+1144h], esi
0x180002b96  add     rsp, 38h
0x180002b9a  pop     rdi
0x180002b9b  pop     rsi
0x180002b9c  pop     rbp
0x180002b9d  pop     rbx
0x180002b9e  retn
```
