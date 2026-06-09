# GenerateHashFromFileHandle

- ea: `0x1800226e4`
- end: `0x180022920`
- name: `GenerateHashFromFileHandle`
- size: `572`
- prototype: `__int64 __fastcall(int, int, int, int, BCRYPT_HASH_HANDLE *phHash, PUCHAR pbInput, ULONG cbInput)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013b90`
- `0x180017d94`
- `0x18001822c`
- `0x180022930`

## callees

- `0x1800100c8`
- `0x180010938`
- `0x18001f8c8`
- `0x18001f944`
- `0x1800226e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002288b`
- `KERNEL32!GetLastError` at `0x18002288b`
- `KERNEL32!SetLastError` at `0x180022807`
- `KERNEL32!SetLastError` at `0x1800228f9`
- `KERNEL32!SetLastError` at `0x180022807`
- `KERNEL32!SetLastError` at `0x1800228f9`
- `KERNEL32!LocalFree` at `0x1800228e5`
- `KERNEL32!LocalFree` at `0x1800228e5`
- `bcrypt!BCryptDestroyHash` at `0x1800228d6`
- `bcrypt!BCryptDestroyHash` at `0x1800228d6`
- `bcrypt!BCryptFinishHash` at `0x1800228bc`
- `bcrypt!BCryptFinishHash` at `0x1800228bc`
- `bcrypt!BCryptHashData` at `0x180022872`
- `bcrypt!BCryptHashData` at `0x180022872`
- `bcrypt!BCryptCreateHash` at `0x180022778`
- `bcrypt!BCryptCreateHash` at `0x180022778`

## pseudocode

```c
__int64 __fastcall GenerateHashFromFileHandle(
        int a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        BCRYPT_HASH_HANDLE *phHash,
        PUCHAR pbInput,
        ULONG cbInput)
{
  BCRYPT_HASH_HANDLE *v7; // r14
  DWORD LastError; // r13d
  __int64 v10; // rbx
  int v11; // r10d
  unsigned int v12; // r12d
  void *AlgHandle; // rsi
  BCRYPT_HASH_HANDLE *v14; // r15
  ULONG v15; // esi
  int v19; // [rsp+C4h] [rbp+54h]

  v19 = HIDWORD(a3);
  v7 = phHash;
  LastError = 0;
  v10 = a3;
  v11 = a1;
  v12 = 1;
  if ( phHash )
  {
    *phHash = 0;
    v7[1] = 0;
    *((_DWORD *)v7 + 4) = 0;
  }
  if ( a3 )
  {
    if ( v7 )
    {
      AlgHandle = (void *)p_GetAlgHandle();
      CngRsa32Compat_Alloc_ALState(AlgHandle, &phHash);
      v14 = phHash;
      if ( BCryptCreateHash(AlgHandle, phHash, (PUCHAR)phHash[1], *((_DWORD *)phHash + 4), 0, 0, 0) < 0 )
        __fastfail(7u);
      v11 = a1;
      *v7 = 0;
      v7[1] = 0;
      *((_DWORD *)v7 + 4) = 0;
    }
    else
    {
      v14 = phHash;
    }
    do
    {
      if ( !v10 )
        break;
      v15 = cbInput;
      if ( !v19 && cbInput > (unsigned int)v10 )
        v15 = v10;
      if ( a4 && a4 == 10485760 * (a4 / 10485760) && (unsigned int)WIMSendMessage(v11, 38030, 0, 0) == -1 )
      {
        SetLastError(0x4D3u);
        v12 = 0;
      }
      if ( v12 && (unsigned int)ReadWriteData(a2, 0) )
      {
        a4 += v15;
        v10 -= v15;
        v19 = HIDWORD(v10);
        if ( v7 && BCryptHashData(*v14, pbInput, v15, 0) < 0 )
          __fastfail(7u);
      }
      else
      {
        LastError = GetLastError();
        v12 = 0;
      }
      v11 = a1;
    }
    while ( v12 );
    if ( v7 )
    {
      if ( BCryptFinishHash(*v14, (PUCHAR)v7, 0x14u, 0) < 0 )
        __fastfail(7u);
      BCryptDestroyHash(*v14);
      LocalFree(v14);
    }
    if ( LastError )
      SetLastError(LastError);
  }
  return v12;
}

```

## disassembly

```asm
0x1800226e4  mov     rax, rsp
0x1800226e7  mov     [rax+20h], rbx
0x1800226eb  mov     [rax+18h], r8
0x1800226ef  mov     [rax+10h], rdx
0x1800226f3  mov     [rax+8], rcx
0x1800226f7  push    rbp
0x1800226f8  push    rsi
0x1800226f9  push    rdi
0x1800226fa  push    r12
0x1800226fc  push    r13
0x1800226fe  push    r14
0x180022700  push    r15
0x180022702  mov     rbp, rsp
0x180022705  sub     rsp, 70h
0x180022709  mov     r14, [rbp+phHash]
0x18002270d  xor     r13d, r13d
0x180022710  mov     rdi, r9
0x180022713  mov     rbx, r8
0x180022716  mov     r10, rcx
0x180022719  mov     r12d, 1
0x18002271f  test    r14, r14
0x180022722  jz      short loc_180022731
0x180022724  xor     eax, eax
0x180022726  mov     [r14], rax
0x180022729  mov     [r14+8], rax
0x18002272d  mov     [r14+10h], eax
0x180022731  test    rbx, rbx
0x180022734  jz      loc_180022905
0x18002273a  mov     [rbp+var_30], r9
0x18002273e  test    r14, r14
0x180022741  jz      short loc_1800227A2
0x180022743  call    p_GetAlgHandle
0x180022748  lea     rdx, [rbp+phHash]
0x18002274c  mov     rcx, rax
0x18002274f  mov     rsi, rax
0x180022752  call    CngRsa32Compat_Alloc_ALState
0x180022757  mov     r15, [rbp+phHash]
0x18002275b  mov     rcx, rsi; hAlgorithm
0x18002275e  and     [rsp+70h+var_40], r13d
0x180022763  mov     rdx, r15; phHash
0x180022766  and     [rsp+70h+var_48], r13d
0x18002276b  and     [rsp+70h+var_50], r13
0x180022770  mov     r9d, [r15+10h]; cbHashObject
0x180022774  mov     r8, [r15+8]; pbHashObject
0x180022778  call    cs:__imp_BCryptCreateHash
0x18002277f  nop     dword ptr [rax+rax+00h]
0x180022784  test    eax, eax
0x180022786  jns     short loc_18002278F
0x180022788  mov     ecx, 7
0x18002278d  int     29h; Win8: RtlFailFast(ecx)
0x18002278f  mov     r10, [rbp+arg_0]
0x180022793  xor     eax, eax
0x180022795  mov     [r14], rax
0x180022798  mov     [r14+8], rax
0x18002279c  mov     [r14+10h], eax
0x1800227a0  jmp     short loc_1800227A6
0x1800227a2  mov     r15, [rbp+phHash]
0x1800227a6  test    rbx, rbx
0x1800227a9  jz      loc_1800228AA
0x1800227af  cmp     [rbp+arg_14], 0
0x1800227b3  mov     esi, [rbp+cbInput]
0x1800227b6  jnz     short loc_1800227BD
0x1800227b8  cmp     esi, ebx
0x1800227ba  cmova   esi, ebx
0x1800227bd  test    rdi, rdi
0x1800227c0  jz      short loc_180022816
0x1800227c2  mov     rax, 6666666666666667h
0x1800227cc  imul    rdi
0x1800227cf  sar     rdx, 16h
0x1800227d3  mov     rax, rdx
0x1800227d6  shr     rax, 3Fh
0x1800227da  add     rdx, rax
0x1800227dd  lea     rcx, [rdx+rdx*4]
0x1800227e1  shl     rcx, 15h
0x1800227e5  cmp     rdi, rcx
0x1800227e8  jnz     short loc_180022816
0x1800227ea  xor     r9d, r9d
0x1800227ed  xor     r8d, r8d
0x1800227f0  mov     edx, 948Eh
0x1800227f5  mov     rcx, r10
0x1800227f8  call    WIMSendMessage
0x1800227fd  cmp     eax, 0FFFFFFFFh
0x180022800  jnz     short loc_180022816
0x180022802  mov     ecx, 4D3h; dwErrCode
0x180022807  call    cs:__imp_SetLastError
0x18002280e  nop     dword ptr [rax+rax+00h]
0x180022813  xor     r12d, r12d
0x180022816  test    r12d, r12d
0x180022819  jz      short loc_18002288B
0x18002281b  mov     eax, dword ptr [rbp+var_30+4]
0x18002281e  lea     r9, [rbp+var_28]
0x180022822  mov     rdx, [rbp+pbInput]
0x180022826  mov     r8d, esi
0x180022829  mov     rcx, [rbp+hFile]; hFile
0x18002282d  and     [rbp+var_28], 0
0x180022832  and     [rbp+var_20], 0
0x180022837  and     [rbp+var_10], 0
0x18002283c  and     dword ptr [rsp+70h+var_50], 0
0x180022841  mov     [rbp+var_14], eax
0x180022844  mov     [rbp+var_18], edi
0x180022847  call    ReadWriteData
0x18002284c  test    eax, eax
0x18002284e  jz      short loc_18002288B
0x180022850  mov     eax, esi
0x180022852  add     rdi, rax
0x180022855  sub     rbx, rax
0x180022858  mov     [rbp+var_30], rdi
0x18002285c  mov     [rbp+50h], rbx
0x180022860  test    r14, r14
0x180022863  jz      short loc_18002289D
0x180022865  mov     rdx, [rbp+pbInput]; pbInput
0x180022869  xor     r9d, r9d; dwFlags
0x18002286c  mov     rcx, [r15]; hHash
0x18002286f  mov     r8d, esi; cbInput
0x180022872  call    cs:__imp_BCryptHashData
0x180022879  nop     dword ptr [rax+rax+00h]
0x18002287e  test    eax, eax
0x180022880  jns     short loc_18002289D
0x180022882  mov     ecx, 7
0x180022887  int     29h; Win8: RtlFailFast(ecx)
0x180022889  jmp     short loc_18002289D
0x18002288b  call    cs:__imp_GetLastError
0x180022892  nop     dword ptr [rax+rax+00h]
0x180022897  mov     r13d, eax
0x18002289a  xor     r12d, r12d
0x18002289d  mov     r10, [rbp+arg_0]
0x1800228a1  test    r12d, r12d
0x1800228a4  jnz     loc_1800227A6
0x1800228aa  test    r14, r14
0x1800228ad  jz      short loc_1800228F1
0x1800228af  mov     rcx, [r15]; hHash
0x1800228b2  xor     r9d, r9d; dwFlags
0x1800228b5  mov     rdx, r14; pbOutput
0x1800228b8  lea     r8d, [r9+14h]; cbOutput
0x1800228bc  call    cs:__imp_BCryptFinishHash
0x1800228c3  nop     dword ptr [rax+rax+00h]
0x1800228c8  test    eax, eax
0x1800228ca  jns     short loc_1800228D3
0x1800228cc  mov     ecx, 7
0x1800228d1  int     29h; Win8: RtlFailFast(ecx)
0x1800228d3  mov     rcx, [r15]; hHash
0x1800228d6  call    cs:__imp_BCryptDestroyHash
0x1800228dd  nop     dword ptr [rax+rax+00h]
0x1800228e2  mov     rcx, r15; hMem
0x1800228e5  call    cs:__imp_LocalFree
0x1800228ec  nop     dword ptr [rax+rax+00h]
0x1800228f1  test    r13d, r13d
0x1800228f4  jz      short loc_180022905
0x1800228f6  mov     ecx, r13d; dwErrCode
0x1800228f9  call    cs:__imp_SetLastError
0x180022900  nop     dword ptr [rax+rax+00h]
0x180022905  mov     rbx, [rsp+70h+arg_18]
0x18002290d  mov     eax, r12d
0x180022910  add     rsp, 70h
0x180022914  pop     r15
0x180022916  pop     r14
0x180022918  pop     r13
0x18002291a  pop     r12
0x18002291c  pop     rdi
0x18002291d  pop     rsi
0x18002291e  pop     rbp
0x18002291f  retn
```
