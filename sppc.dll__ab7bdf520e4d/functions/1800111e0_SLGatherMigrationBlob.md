# SLGatherMigrationBlob

- ea: `0x1800111e0`
- end: `0x180011282`
- name: `SLGatherMigrationBlob`
- size: `162`
- prototype: `HRESULT __stdcall(BOOL bMigratableOnly, LPCWSTR pwszEncryptorUri, HANDLE hFile)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001430`
- `0x1800021b0`
- `0x180002610`
- `0x180006844`
- `0x18000a8d0`
- `0x1800111e0`
- `0x180011290`

## pseudocode

```c
HRESULT __stdcall SLGatherMigrationBlob(BOOL bMigratableOnly, LPCWSTR pwszEncryptorUri, HANDLE hFile)
{
  int v6; // ebx

  if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v6 = -2147024809;
    sub_180006844(2147942487LL);
    sub_180002610(qword_180018588, qword_18001E740);
  }
  else
  {
    sub_1800021B0(byte_18001A2B0, qword_18001E110);
    v6 = SLGatherMigrationBlobEx(bMigratableOnly ? 1 : -1, pwszEncryptorUri, hFile);
    sub_180001430(qword_180018E98, byte_18001E400);
    if ( v6 < 0 )
      sub_180006844((unsigned int)v6);
  }
  sub_18000A8D0((unsigned int)v6);
  return v6;
}

```

## disassembly

```asm
0x1800111e0  mov     [rsp+arg_0], rbx
0x1800111e5  mov     [rsp+arg_8], rsi
0x1800111ea  push    rdi
0x1800111eb  sub     rsp, 20h
0x1800111ef  lea     rax, [r8-1]
0x1800111f3  mov     rbx, r8
0x1800111f6  mov     rsi, rdx
0x1800111f9  mov     edi, ecx
0x1800111fb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800111ff  ja      short loc_18001124A
0x180011201  lea     rdx, qword_18001E110
0x180011208  lea     rcx, byte_18001A2B0
0x18001120f  call    sub_1800021B0
0x180011214  neg     edi
0x180011216  mov     r8, rbx; hFile
0x180011219  mov     rdx, rsi; pwszEncryptorUri
0x18001121c  sbb     ecx, ecx
0x18001121e  and     ecx, 2
0x180011221  dec     ecx; dwFlags
0x180011223  call    SLGatherMigrationBlobEx
0x180011228  lea     rdx, byte_18001E400
0x18001122f  mov     ebx, eax
0x180011231  lea     rcx, qword_180018E98
0x180011238  call    sub_180001430
0x18001123d  test    ebx, ebx
0x18001123f  jns     short loc_180011269
0x180011241  mov     ecx, ebx
0x180011243  call    sub_180006844
0x180011248  jmp     short loc_180011269
0x18001124a  mov     ebx, 80070057h
0x18001124f  mov     ecx, ebx
0x180011251  call    sub_180006844
0x180011256  lea     rdx, qword_18001E740
0x18001125d  lea     rcx, qword_180018588
0x180011264  call    sub_180002610
0x180011269  mov     ecx, ebx
0x18001126b  call    sub_18000A8D0
0x180011270  mov     rsi, [rsp+28h+arg_8]
0x180011275  mov     eax, ebx
0x180011277  mov     rbx, [rsp+28h+arg_0]
0x18001127c  add     rsp, 20h
0x180011280  pop     rdi
0x180011281  retn
```
