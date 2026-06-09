# SLGatherMigrationBlobEx

- ea: `0x180011290`
- end: `0x1800113cf`
- name: `SLGatherMigrationBlobEx`
- size: `319`
- prototype: `HRESULT __stdcall(DWORD dwFlags, LPCWSTR pwszEncryptorUri, HANDLE hFile)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800111e0`

## callees

- `0x180001ec0`
- `0x180002bf0`
- `0x180003410`
- `0x1800044dc`
- `0x180004f80`
- `0x180004fbc`
- `0x180005208`
- `0x1800052b4`
- `0x180006844`
- `0x18000a8d0`
- `0x18000f144`
- `0x180011290`
- `0x180013060`

## pseudocode

```c
HRESULT __stdcall SLGatherMigrationBlobEx(DWORD dwFlags, LPCWSTR pwszEncryptorUri, HANDLE hFile)
{
  int v5; // eax
  HRESULT v6; // ebx
  __int64 v7; // rcx
  __int64 v9[2]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v10; // [rsp+40h] [rbp-10h] BYREF
  DWORD v11; // [rsp+70h] [rbp+20h] BYREF
  HANDLE v12; // [rsp+80h] [rbp+30h] BYREF
  HSLC phSLC; // [rsp+88h] [rbp+38h] BYREF

  v12 = hFile;
  v11 = dwFlags;
  phSLC = 0;
  v10 = 0;
  sub_180001EC0(byte_180018758, byte_18001E918);
  v9[0] = (__int64)&v10 + 8;
  v9[1] = (__int64)&v10;
  if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v6 = -2147024809;
    v7 = 2147942487LL;
    goto LABEL_11;
  }
  v5 = SLOpen(&phSLC);
  v6 = v5;
  if ( v5 < 0
    || (v5 = sub_180004F80(v9, 1, &v11), v6 = v5, v5 < 0)
    || (v5 = sub_18000F144(v9, 2, pwszEncryptorUri), v6 = v5, v5 < 0) )
  {
LABEL_3:
    v7 = (unsigned int)v5;
LABEL_11:
    sub_180006844(v7);
    goto LABEL_12;
  }
  v6 = sub_180004FBC(v9, 3, &v12);
  if ( v6 >= 0 )
  {
    v5 = sub_1800044DC(v9, (__int64)phSLC, 0x2Fu, 1, 1);
    v6 = v5;
    if ( v5 >= 0 )
      goto LABEL_12;
    goto LABEL_3;
  }
  sub_180002BF0(byte_180018B48, &dword_18001E6BC);
  sub_180006844((unsigned int)v6);
  sub_180003410(qword_1800185D0, qword_18001E7B8);
LABEL_12:
  sub_18000A8D0((unsigned int)v6);
  sub_180005208(v9);
  sub_1800052B4(&phSLC);
  return v6;
}

```

## disassembly

```asm
0x180011290  mov     [rsp-18h+arg_10], r8
0x180011295  mov     [rsp-18h+arg_0], ecx
0x180011299  push    rbp
0x18001129a  push    rbx
0x18001129b  push    rdi
0x18001129c  mov     rbp, rsp
0x18001129f  sub     rsp, 50h
0x1800112a3  mov     rdi, rdx
0x1800112a6  mov     [rbp+phSLC], 0
0x1800112ae  xorps   xmm0, xmm0
0x1800112b1  lea     rdx, byte_18001E918
0x1800112b8  lea     rcx, byte_180018758
0x1800112bf  mov     rbx, r8
0x1800112c2  movdqu  [rbp+var_10], xmm0
0x1800112c7  call    sub_180001EC0
0x1800112cc  lea     rax, [rbp+var_10+8]
0x1800112d0  mov     [rbp+var_20], rax
0x1800112d4  lea     rax, [rbp+var_10]
0x1800112d8  mov     [rbp+var_18], rax
0x1800112dc  lea     rax, [rbx-1]
0x1800112e0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800112e4  ja      loc_1800113A0
0x1800112ea  lea     rcx, [rbp+phSLC]; phSLC
0x1800112ee  call    SLOpen
0x1800112f3  mov     ebx, eax
0x1800112f5  test    eax, eax
0x1800112f7  jns     short loc_180011300
0x1800112f9  mov     ecx, eax
0x1800112fb  jmp     loc_1800113A7
0x180011300  lea     r8, [rbp+arg_0]
0x180011304  mov     edx, 1
0x180011309  lea     rcx, [rbp+var_20]
0x18001130d  call    sub_180004F80
0x180011312  mov     ebx, eax
0x180011314  test    eax, eax
0x180011316  js      short loc_1800112F9
0x180011318  mov     r8, rdi
0x18001131b  lea     rcx, [rbp+var_20]
0x18001131f  mov     edx, 2
0x180011324  call    sub_18000F144
0x180011329  mov     ebx, eax
0x18001132b  test    eax, eax
0x18001132d  js      short loc_1800112F9
0x18001132f  lea     r8, [rbp+arg_10]
0x180011333  mov     edx, 3
0x180011338  lea     rcx, [rbp+var_20]
0x18001133c  call    sub_180004FBC
0x180011341  mov     ebx, eax
0x180011343  test    eax, eax
0x180011345  jns     short loc_180011376
0x180011347  lea     rdx, dword_18001E6BC
0x18001134e  lea     rcx, byte_180018B48
0x180011355  call    sub_180002BF0
0x18001135a  mov     ecx, ebx
0x18001135c  call    sub_180006844
0x180011361  lea     rdx, qword_18001E7B8
0x180011368  lea     rcx, qword_1800185D0
0x18001136f  call    sub_180003410
0x180011374  jmp     short loc_1800113AC
0x180011376  mov     rdx, [rbp+phSLC]
0x18001137a  lea     rcx, [rbp+var_20]
0x18001137e  mov     r9d, 1
0x180011384  mov     [rsp+50h+var_30], 1
0x18001138c  lea     r8d, [r9+2Eh]
0x180011390  call    sub_1800044DC
0x180011395  mov     ebx, eax
0x180011397  test    eax, eax
0x180011399  jns     short loc_1800113AC
0x18001139b  jmp     loc_1800112F9
0x1800113a0  mov     ebx, 80070057h
0x1800113a5  mov     ecx, ebx
0x1800113a7  call    sub_180006844
0x1800113ac  mov     ecx, ebx
0x1800113ae  call    sub_18000A8D0
0x1800113b3  lea     rcx, [rbp+var_20]
0x1800113b7  call    sub_180005208
0x1800113bc  lea     rcx, [rbp+phSLC]
0x1800113c0  call    sub_1800052B4
0x1800113c5  mov     eax, ebx
0x1800113c7  add     rsp, 50h
0x1800113cb  pop     rdi
0x1800113cc  pop     rbx
0x1800113cd  pop     rbp
0x1800113ce  retn
```
