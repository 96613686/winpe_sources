# SLFreeTokenActivationCertificates

- ea: `0x18003d900`
- end: `0x18003d9e7`
- name: `SLFreeTokenActivationCertificates`
- size: `231`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003b1d0`

## callees

- `0x180006c10`
- `0x18003d900`
- `0x180042514`
- `0x1800427f4`
- `0x180042acc`
- `0x180042db0`
- `0x180043088`
- `0x180043bd8`
- `0x180043eac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d9a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d9a2`
- `CRYPT32!CertFreeCertificateContext` at `0x18003d98a`
- `CRYPT32!CertFreeCertificateContext` at `0x18003d98a`

## pseudocode

```c
__int64 __fastcall SLFreeTokenActivationCertificates(_QWORD *hMem, __int64 a2, __int64 a3)
{
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r8
  const CERT_CONTEXT *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r8

  sub_1800427F4((unsigned int *)&dword_1800846B4, (unsigned int *)byte_18008D2F8, a3);
  if ( hMem )
  {
    sub_180042ACC((unsigned int *)&dword_18008263C, (unsigned int *)qword_18008D100, v4);
    sub_180043BD8((unsigned int *)byte_180084070, (unsigned int *)qword_18008CBE0, v5);
    v6 = 0;
    sub_180042DB0((unsigned int *)&dword_1800811C4, (unsigned int *)qword_18008DB08, v7);
    if ( *(_DWORD *)hMem )
    {
      sub_180043088((unsigned int *)byte_180082A70, (unsigned int *)qword_18008D440, v8);
      do
      {
        v9 = (const CERT_CONTEXT *)hMem[v6 + 1];
        if ( v9 )
        {
          CertFreeCertificateContext(v9);
          hMem[v6 + 1] = 0;
        }
        v6 = (unsigned int)(v6 + 1);
      }
      while ( (unsigned int)v6 < *(_DWORD *)hMem );
    }
    LocalFree(hMem);
    sub_180042514((unsigned int *)qword_1800836C0, (unsigned int *)qword_18008DE10, v10);
  }
  sub_180006C10(0);
  sub_180043EAC((unsigned int *)&dword_180085734, (unsigned int *)byte_18008CD18, v11);
  return 0;
}

```

## disassembly

```asm
0x18003d900  mov     [rsp+arg_0], rbx
0x18003d905  mov     [rsp+arg_8], rsi
0x18003d90a  push    rdi
0x18003d90b  sub     rsp, 20h
0x18003d90f  mov     rbx, rcx
0x18003d912  lea     rdx, byte_18008D2F8
0x18003d919  lea     rcx, dword_1800846B4
0x18003d920  call    sub_1800427F4
0x18003d925  test    rbx, rbx
0x18003d928  jz      loc_18003D9BB
0x18003d92e  lea     rdx, qword_18008D100
0x18003d935  lea     rcx, dword_18008263C
0x18003d93c  call    sub_180042ACC
0x18003d941  lea     rdx, qword_18008CBE0
0x18003d948  lea     rcx, byte_180084070
0x18003d94f  call    sub_180043BD8
0x18003d954  lea     rdx, qword_18008DB08
0x18003d95b  xor     edi, edi
0x18003d95d  lea     rcx, dword_1800811C4
0x18003d964  call    sub_180042DB0
0x18003d969  cmp     [rbx], edi
0x18003d96b  jbe     short loc_18003D99F
0x18003d96d  lea     rdx, qword_18008D440
0x18003d974  lea     rcx, byte_180082A70
0x18003d97b  call    sub_180043088
0x18003d980  mov     rcx, [rbx+rdi*8+8]; pCertContext
0x18003d985  test    rcx, rcx
0x18003d988  jz      short loc_18003D999
0x18003d98a  call    cs:CertFreeCertificateContext
0x18003d990  mov     qword ptr [rbx+rdi*8+8], 0
0x18003d999  inc     edi
0x18003d99b  cmp     edi, [rbx]
0x18003d99d  jb      short loc_18003D980
0x18003d99f  mov     rcx, rbx; hMem
0x18003d9a2  call    cs:LocalFree
0x18003d9a8  lea     rdx, qword_18008DE10
0x18003d9af  lea     rcx, qword_1800836C0
0x18003d9b6  call    sub_180042514
0x18003d9bb  xor     ecx, ecx
0x18003d9bd  call    sub_180006C10
0x18003d9c2  lea     rdx, byte_18008CD18
0x18003d9c9  lea     rcx, dword_180085734
0x18003d9d0  call    sub_180043EAC
0x18003d9d5  mov     rbx, [rsp+28h+arg_0]
0x18003d9da  xor     eax, eax
0x18003d9dc  mov     rsi, [rsp+28h+arg_8]
0x18003d9e1  add     rsp, 20h
0x18003d9e5  pop     rdi
0x18003d9e6  retn
```
