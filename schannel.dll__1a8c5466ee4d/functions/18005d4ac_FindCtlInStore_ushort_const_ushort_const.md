# FindCtlInStore(ushort const *,ushort const *)

- ea: `0x18005d4ac`
- end: `0x18005d5df`
- name: `?FindCtlInStore@@YAPEBU_CTL_CONTEXT@@PEBG0@Z`
- size: `307`
- prototype: `const struct _CTL_CONTEXT *__fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004fa40`

## callees

- `0x18004be74`
- `0x18005d4ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d5a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d5a1`
- `CRYPT32!CertOpenStore` at `0x18005d4de`
- `CRYPT32!CertOpenStore` at `0x18005d4de`
- `CRYPT32!CertCloseStore` at `0x18005d5cd`
- `CRYPT32!CertCloseStore` at `0x18005d5cd`
- `CRYPT32!CertFindCTLInStore` at `0x18005d57a`
- `CRYPT32!CertFindCTLInStore` at `0x18005d57a`

## pseudocode

```c
PCCTL_CONTEXT __fastcall FindCtlInStore(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int v3; // esi
  HCERTSTORE v4; // rdi
  char v5; // al
  __int64 v7; // rax
  PCCTL_CONTEXT CTLInStore; // rsi
  char LastError; // al
  __int128 pvFindPara; // [rsp+30h] [rbp-58h] BYREF
  __int128 v11; // [rsp+40h] [rbp-48h]
  __int128 v12; // [rsp+50h] [rbp-38h]

  v3 = (int)a1;
  pvFindPara = 0;
  v11 = 0;
  v12 = 0;
  v4 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, a1);
  if ( v4 )
  {
    LODWORD(pvFindPara) = 48;
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    DWORD2(v11) = 2 * v7 + 2;
    *(_QWORD *)&v12 = a2;
    CTLInStore = CertFindCTLInStore(v4, 0x10001u, 0, 3u, &pvFindPara, 0);
    if ( !CTLInStore
      && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_373d12f1978338b61962a9e735bda8d8_Traceguids,
        (_DWORD)a2,
        LastError);
    }
    CertCloseStore(v4, 0);
    return CTLInStore;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_373d12f1978338b61962a9e735bda8d8_Traceguids,
        v3,
        v5);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18005d4ac  mov     rax, rsp
0x18005d4af  push    rbx
0x18005d4b0  push    rbp
0x18005d4b1  push    rsi
0x18005d4b2  push    rdi
0x18005d4b3  sub     rsp, 68h
0x18005d4b7  xorps   xmm0, xmm0
0x18005d4ba  mov     [rax-68h], rcx
0x18005d4be  mov     rbx, rdx
0x18005d4c1  mov     rsi, rcx
0x18005d4c4  xor     edx, edx; dwEncodingType
0x18005d4c6  mov     r9d, 20000h; dwFlags
0x18005d4cc  xor     r8d, r8d; hCryptProv
0x18005d4cf  movups  xmmword ptr [rax-58h], xmm0
0x18005d4d3  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18005d4d6  movups  xmmword ptr [rax-48h], xmm0
0x18005d4da  movups  xmmword ptr [rax-38h], xmm0
0x18005d4de  call    cs:__imp_CertOpenStore
0x18005d4e4  xor     ebp, ebp
0x18005d4e6  mov     rdi, rax
0x18005d4e9  test    rax, rax
0x18005d4ec  jnz     short loc_18005D535
0x18005d4ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d4f5  lea     rax, WPP_GLOBAL_Control
0x18005d4fc  cmp     rcx, rax
0x18005d4ff  jz      short loc_18005D52E
0x18005d501  test    byte ptr [rcx+1Ch], 1
0x18005d505  jz      short loc_18005D52E
0x18005d507  call    cs:__imp_GetLastError
0x18005d50d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d514  lea     edx, [rdi+0Ah]
0x18005d517  mov     r9, rsi
0x18005d51a  mov     dword ptr [rsp+88h+pvFindPara], eax
0x18005d51e  lea     r8, WPP_373d12f1978338b61962a9e735bda8d8_Traceguids
0x18005d525  mov     rcx, [rcx+10h]
0x18005d529  call    WPP_SF_Sd
0x18005d52e  xor     eax, eax
0x18005d530  jmp     loc_18005D5D6
0x18005d535  mov     dword ptr [rsp+88h+var_58], 30h ; '0'
0x18005d53d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005d541  inc     rax
0x18005d544  cmp     [rbx+rax*2], bp
0x18005d548  jnz     short loc_18005D541
0x18005d54a  lea     eax, ds:2[rax*2]
0x18005d551  mov     [rsp+88h+pPrevCtlContext], rbp; pPrevCtlContext
0x18005d556  mov     [rsp+88h+var_40], eax
0x18005d55a  mov     r9d, 3; dwFindType
0x18005d560  lea     rax, [rsp+88h+var_58]
0x18005d565  mov     qword ptr [rsp+88h+var_38], rbx
0x18005d56a  xor     r8d, r8d; dwFindFlags
0x18005d56d  mov     [rsp+88h+pvFindPara], rax; pvFindPara
0x18005d572  mov     edx, 10001h; dwMsgAndCertEncodingType
0x18005d577  mov     rcx, rdi; hCertStore
0x18005d57a  call    cs:__imp_CertFindCTLInStore
0x18005d580  mov     rsi, rax
0x18005d583  test    rax, rax
0x18005d586  jnz     short loc_18005D5C8
0x18005d588  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d58f  lea     rax, WPP_GLOBAL_Control
0x18005d596  cmp     rcx, rax
0x18005d599  jz      short loc_18005D5C8
0x18005d59b  test    byte ptr [rcx+1Ch], 2
0x18005d59f  jz      short loc_18005D5C8
0x18005d5a1  call    cs:__imp_GetLastError
0x18005d5a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d5ae  lea     edx, [rsi+0Bh]
0x18005d5b1  mov     r9, rbx
0x18005d5b4  mov     dword ptr [rsp+88h+pvFindPara], eax
0x18005d5b8  lea     r8, WPP_373d12f1978338b61962a9e735bda8d8_Traceguids
0x18005d5bf  mov     rcx, [rcx+10h]
0x18005d5c3  call    WPP_SF_Sd
0x18005d5c8  xor     edx, edx; dwFlags
0x18005d5ca  mov     rcx, rdi; hCertStore
0x18005d5cd  call    cs:__imp_CertCloseStore
0x18005d5d3  mov     rax, rsi
0x18005d5d6  add     rsp, 68h
0x18005d5da  pop     rdi
0x18005d5db  pop     rsi
0x18005d5dc  pop     rbp
0x18005d5dd  pop     rbx
0x18005d5de  retn
```
