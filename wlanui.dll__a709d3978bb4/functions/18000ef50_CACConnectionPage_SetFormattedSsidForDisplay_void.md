# CACConnectionPage::SetFormattedSsidForDisplay(void)

- ea: `0x18000ef50`
- end: `0x18000f174`
- name: `?SetFormattedSsidForDisplay@CACConnectionPage@@AEAAXXZ`
- size: `548`
- prototype: `void __fastcall(CACConnectionPage *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000e31c`

## callees

- `0x180001e26`
- `0x18000db78`
- `0x18000ef50`
- `0x18001bf0a`
- `0x18001bf40`

## import_xrefs

- `msvcrt!mbtowc` at `0x18000f002`
- `msvcrt!mbtowc` at `0x18000f016`
- `msvcrt!mbtowc` at `0x18000f02a`
- `msvcrt!mbtowc` at `0x18000f03a`
- `msvcrt!mbtowc` at `0x18000f12d`
- `msvcrt!mbtowc` at `0x18000f002`
- `msvcrt!mbtowc` at `0x18000f016`
- `msvcrt!mbtowc` at `0x18000f02a`
- `msvcrt!mbtowc` at `0x18000f03a`
- `msvcrt!mbtowc` at `0x18000f12d`
- `KERNEL32!GetProcessHeap` at `0x18000f045`
- `KERNEL32!GetProcessHeap` at `0x18000f143`
- `KERNEL32!GetProcessHeap` at `0x18000f045`
- `KERNEL32!GetProcessHeap` at `0x18000f143`
- `KERNEL32!HeapFree` at `0x18000f053`
- `KERNEL32!HeapFree` at `0x18000f151`
- `KERNEL32!HeapFree` at `0x18000f053`
- `KERNEL32!HeapFree` at `0x18000f151`
- `USER32!SetWindowTextW` at `0x18000f061`
- `USER32!SetWindowTextW` at `0x18000f061`

## pseudocode

```c
void __fastcall CACConnectionPage::SetFormattedSsidForDisplay(CACConnectionPage *this)
{
  __int64 v2; // r15
  void *v3; // rbx
  __int64 v4; // rdx
  _OWORD *v5; // rdx
  __int64 v6; // rdi
  HANDLE v7; // rax
  int v8; // esi
  unsigned int v9; // r14d
  unsigned int v10; // edx
  wchar_t *v11; // r9
  __int64 v12; // rax
  unsigned __int64 v13; // rcx
  HANDLE ProcessHeap; // rax
  char SrcCh; // [rsp+20h] [rbp-59h] BYREF
  char v16[7]; // [rsp+21h] [rbp-58h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-51h] BYREF
  WCHAR String[8]; // [rsp+30h] [rbp-49h] BYREF
  __int128 v19; // [rsp+40h] [rbp-39h]
  __int128 v20; // [rsp+50h] [rbp-29h]
  wchar_t DstCh[8]; // [rsp+60h] [rbp-19h] BYREF
  wchar_t v22[8]; // [rsp+70h] [rbp-9h] BYREF

  v2 = *(_QWORD *)(*((_QWORD *)this + 18) + 552LL);
  memset_0(String, 0, 0x42u);
  v16[0] = 44;
  SrcCh = 46;
  v3 = 0;
  v4 = *(_QWORD *)(v2 + 8);
  lpMem = 0;
  if ( *(_DWORD *)(v4 + 4) == 1 )
  {
    v5 = (_OWORD *)*((_QWORD *)this + 17);
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)v5 + v6) );
    if ( (unsigned int)v6 > 0x20 )
    {
      *(_OWORD *)String = *v5;
      v19 = v5[1];
      v20 = v5[2];
      *(_OWORD *)DstCh = v5[3];
LABEL_6:
      mbtowc(&DstCh[5], &SrcCh, 1u);
      mbtowc(&DstCh[6], &SrcCh, 1u);
      mbtowc(&DstCh[7], &SrcCh, 1u);
      goto LABEL_7;
    }
    memcpy_0(String, v5, 2LL * (unsigned int)v6);
  }
  else if ( *(_DWORD *)(v4 + 4) )
  {
    v8 = 0;
    v9 = 0;
    while ( 1 )
    {
      CACConnectionPage::ConvertProfileSsidToDisplaySsid(
        (CACConnectionPage *)(9LL * v9),
        (struct _DOT11_SSID *)(v4 + 36LL * v9 + 12),
        (unsigned __int16 **)&lpMem);
      v3 = lpMem;
      v10 = 0;
      v11 = &String[v8];
      v12 = -1;
      do
        ++v12;
      while ( *((_WORD *)lpMem + v12) );
      if ( v12 )
        break;
LABEL_20:
      if ( v9 != *(_DWORD *)(*(_QWORD *)(v2 + 8) + 4LL) - 1 )
      {
        mbtowc(v11, v16, 1u);
        if ( ++v8 == 32 )
          goto LABEL_6;
      }
      if ( v3 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v3);
        v3 = 0;
        lpMem = 0;
      }
      v4 = *(_QWORD *)(v2 + 8);
      if ( ++v9 >= *(_DWORD *)(v4 + 4) )
        goto LABEL_7;
    }
    while ( 1 )
    {
      ++v8;
      *v11 = *((_WORD *)v3 + v10);
      if ( v8 == 32 )
        goto LABEL_6;
      ++v11;
      v13 = -1;
      ++v10;
      do
        ++v13;
      while ( *((_WORD *)v3 + v13) );
      if ( v10 >= v13 )
        goto LABEL_20;
    }
  }
LABEL_7:
  mbtowc(v22, 0, 1u);
  if ( v3 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v3);
  }
  SetWindowTextW(*((HWND *)this + 4), String);
}

```

## disassembly

```asm
0x18000ef50  push    rbp
0x18000ef52  push    rbx
0x18000ef53  push    rsi
0x18000ef54  push    rdi
0x18000ef55  push    r12
0x18000ef57  push    r13
0x18000ef59  push    r14
0x18000ef5b  push    r15
0x18000ef5d  lea     rbp, [rsp-1Fh]
0x18000ef62  sub     rsp, 98h
0x18000ef69  mov     rax, cs:__security_cookie
0x18000ef70  xor     rax, rsp
0x18000ef73  mov     [rbp+57h+var_50], rax
0x18000ef77  mov     rax, [rcx+90h]
0x18000ef7e  xor     edx, edx; Val
0x18000ef80  mov     r13, rcx
0x18000ef83  lea     rcx, [rbp+57h+String]; void *
0x18000ef87  mov     r15, [rax+228h]
0x18000ef8e  lea     r8d, [rdx+42h]; Size
0x18000ef92  call    memset_0
0x18000ef97  mov     [rbp+57h+var_AF], 2Ch ; ','
0x18000ef9b  xor     r12d, r12d
0x18000ef9e  mov     [rbp+57h+SrcCh], 2Eh ; '.'
0x18000efa2  mov     ebx, r12d
0x18000efa5  mov     rdx, [r15+8]
0x18000efa9  mov     [rbp+57h+lpMem], rbx
0x18000efad  cmp     dword ptr [rdx+4], 1
0x18000efb1  jnz     loc_18000F098
0x18000efb7  mov     rdx, [r13+88h]; Src
0x18000efbe  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000efc2  inc     rdi
0x18000efc5  cmp     [rdx+rdi*2], r12w
0x18000efca  jnz     short loc_18000EFC2
0x18000efcc  cmp     edi, 20h ; ' '
0x18000efcf  jbe     loc_18000F087
0x18000efd5  movups  xmm0, xmmword ptr [rdx]
0x18000efd8  movaps  xmmword ptr [rbp+57h+String], xmm0
0x18000efdc  movups  xmm1, xmmword ptr [rdx+10h]
0x18000efe0  movaps  [rbp+57h+var_90], xmm1
0x18000efe4  movups  xmm0, xmmword ptr [rdx+20h]
0x18000efe8  movaps  [rbp+57h+var_80], xmm0
0x18000efec  movups  xmm1, xmmword ptr [rdx+30h]
0x18000eff0  movaps  xmmword ptr [rbp+57h+DstCh], xmm1
0x18000eff4  mov     r8d, 1; SrcSizeInBytes
0x18000effa  lea     rdx, [rbp+57h+SrcCh]; SrcCh
0x18000effe  lea     rcx, [rbp+57h+DstCh+0Ah]; DstCh
0x18000f002  call    cs:__imp_mbtowc
0x18000f008  mov     r8d, 1; SrcSizeInBytes
0x18000f00e  lea     rdx, [rbp+57h+SrcCh]; SrcCh
0x18000f012  lea     rcx, [rbp+57h+DstCh+0Ch]; DstCh
0x18000f016  call    cs:__imp_mbtowc
0x18000f01c  mov     r8d, 1; SrcSizeInBytes
0x18000f022  lea     rdx, [rbp+57h+SrcCh]; SrcCh
0x18000f026  lea     rcx, [rbp+57h+DstCh+0Eh]; DstCh
0x18000f02a  call    cs:__imp_mbtowc
0x18000f030  xor     edx, edx; SrcCh
0x18000f032  lea     rcx, [rbp+57h+var_60]; DstCh
0x18000f036  lea     r8d, [rdx+1]; SrcSizeInBytes
0x18000f03a  call    cs:__imp_mbtowc
0x18000f040  test    rbx, rbx
0x18000f043  jz      short loc_18000F059
0x18000f045  call    cs:__imp_GetProcessHeap
0x18000f04b  mov     r8, rbx; lpMem
0x18000f04e  xor     edx, edx; dwFlags
0x18000f050  mov     rcx, rax; hHeap
0x18000f053  call    cs:__imp_HeapFree
0x18000f059  mov     rcx, [r13+20h]; hWnd
0x18000f05d  lea     rdx, [rbp+57h+String]; lpString
0x18000f061  call    cs:__imp_SetWindowTextW
0x18000f067  mov     rcx, [rbp+57h+var_50]
0x18000f06b  xor     rcx, rsp; StackCookie
0x18000f06e  call    __security_check_cookie
0x18000f073  add     rsp, 98h
0x18000f07a  pop     r15
0x18000f07c  pop     r14
0x18000f07e  pop     r13
0x18000f080  pop     r12
0x18000f082  pop     rdi
0x18000f083  pop     rsi
0x18000f084  pop     rbx
0x18000f085  pop     rbp
0x18000f086  retn
0x18000f087  mov     r8d, edi
0x18000f08a  lea     rcx, [rbp+57h+String]; void *
0x18000f08e  add     r8, r8; Size
0x18000f091  call    memcpy_0
0x18000f096  jmp     short loc_18000F030
0x18000f098  cmp     [rdx+4], r12d
0x18000f09c  jbe     short loc_18000F030
0x18000f09e  mov     esi, r12d
0x18000f0a1  mov     r14d, r12d
0x18000f0a4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000f0a8  mov     eax, r14d
0x18000f0ab  lea     r8, [rbp+57h+lpMem]; unsigned __int16 **
0x18000f0af  lea     rcx, [rax+rax*8]; this
0x18000f0b3  lea     rdx, [rdx+rcx*4]
0x18000f0b7  add     rdx, 0Ch; struct _DOT11_SSID *
0x18000f0bb  call    ?ConvertProfileSsidToDisplaySsid@CACConnectionPage@@AEAAKPEAU_DOT11_SSID@@PEAPEAG@Z; CACConnectionPage::ConvertProfileSsidToDisplaySsid(_DOT11_SSID *,ushort * *)
0x18000f0c0  mov     rbx, [rbp+57h+lpMem]
0x18000f0c4  lea     r9, [rbp+57h+String]
0x18000f0c8  mov     eax, esi
0x18000f0ca  mov     edx, r12d
0x18000f0cd  lea     r9, [r9+rax*2]
0x18000f0d1  mov     rax, rdi
0x18000f0d4  inc     rax
0x18000f0d7  cmp     [rbx+rax*2], r12w
0x18000f0dc  jnz     short loc_18000F0D4
0x18000f0de  test    rax, rax
0x18000f0e1  jz      short loc_18000F112
0x18000f0e3  mov     eax, edx
0x18000f0e5  inc     esi
0x18000f0e7  movzx   ecx, word ptr [rbx+rax*2]
0x18000f0eb  mov     [r9], cx
0x18000f0ef  cmp     esi, 20h ; ' '
0x18000f0f2  jz      loc_18000EFF4
0x18000f0f8  add     r9, 2
0x18000f0fc  mov     rcx, rdi
0x18000f0ff  inc     edx
0x18000f101  inc     rcx
0x18000f104  cmp     [rbx+rcx*2], r12w
0x18000f109  jnz     short loc_18000F101
0x18000f10b  mov     eax, edx
0x18000f10d  cmp     rax, rcx
0x18000f110  jb      short loc_18000F0E3
0x18000f112  mov     rax, [r15+8]
0x18000f116  mov     ecx, [rax+4]
0x18000f119  dec     ecx
0x18000f11b  cmp     r14d, ecx
0x18000f11e  jz      short loc_18000F13E
0x18000f120  mov     r8d, 1; SrcSizeInBytes
0x18000f126  lea     rdx, [rbp+57h+var_AF]; SrcCh
0x18000f12a  mov     rcx, r9; DstCh
0x18000f12d  call    cs:__imp_mbtowc
0x18000f133  inc     esi
0x18000f135  cmp     esi, 20h ; ' '
0x18000f138  jz      loc_18000EFF4
0x18000f13e  test    rbx, rbx
0x18000f141  jz      short loc_18000F15E
0x18000f143  call    cs:__imp_GetProcessHeap
0x18000f149  mov     r8, rbx; lpMem
0x18000f14c  xor     edx, edx; dwFlags
0x18000f14e  mov     rcx, rax; hHeap
0x18000f151  call    cs:__imp_HeapFree
0x18000f157  mov     rbx, r12
0x18000f15a  mov     [rbp+57h+lpMem], rbx
0x18000f15e  mov     rdx, [r15+8]
0x18000f162  inc     r14d
0x18000f165  cmp     r14d, [rdx+4]
0x18000f169  jb      loc_18000F0A8
0x18000f16f  jmp     loc_18000F030
```
