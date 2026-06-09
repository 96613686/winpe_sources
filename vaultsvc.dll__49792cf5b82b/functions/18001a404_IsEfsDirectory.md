# IsEfsDirectory

- ea: `0x18001a404`
- end: `0x18001a62c`
- name: `IsEfsDirectory`
- size: `552`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180019ef0`

## callees

- `0x180003140`
- `0x18001a404`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18004b43c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a4b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a4b2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001a47f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001a4dd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001a47f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001a4dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsEfsDirectory(const WCHAR *Src, DWORD *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  unsigned int v6; // ebx
  DWORD FileAttributesW; // eax
  WCHAR *v9; // rax
  const WCHAR *v10; // r15
  DWORD LastError; // eax
  PVOID *v12; // rcx
  __int64 i; // rbx
  __int64 v14; // [rsp+20h] [rbp-58h] BYREF
  WCHAR *v15; // [rsp+28h] [rbp-50h]
  int v16; // [rsp+30h] [rbp-48h]

  v15 = 0;
  v16 = 0;
  v14 = 0;
  if ( !Src )
    goto LABEL_5;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( Src[v5] );
  if ( !v5 )
  {
LABEL_5:
    v6 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e65014c76418321bb93a76a498c7a7da_Traceguids, 87);
LABEL_6:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
    return v6;
  }
  FileAttributesW = GetFileAttributesW(Src);
  if ( FileAttributesW == -1 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e65014c76418321bb93a76a498c7a7da_Traceguids);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    do
      ++v4;
    while ( Src[v4] );
    for ( i = (unsigned int)(v4 - 1); ; i = (unsigned int)(i - 1) )
    {
      if ( (int)i < 1 )
      {
        v6 = 87;
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
          WPP_SF_d(v12[2], 12, WPP_e65014c76418321bb93a76a498c7a7da_Traceguids, 87);
        goto LABEL_6;
      }
      if ( Src[i] == 92 )
        break;
    }
    v9 = (WCHAR *)LocalAlloc(0x40u, 2LL * (unsigned int)(i + 1));
    v10 = v9;
    v15 = v9;
    if ( v9 )
    {
      memcpy_0(v9, Src, 2LL * (unsigned int)i);
      FileAttributesW = GetFileAttributesW(v10);
      if ( FileAttributesW != -1 )
        goto LABEL_8;
      LastError = GetLastError();
      v6 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_e65014c76418321bb93a76a498c7a7da_Traceguids, LastError);
      goto LABEL_6;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_e65014c76418321bb93a76a498c7a7da_Traceguids, 14);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
    return 14;
  }
  else
  {
LABEL_8:
    *a2 = (FileAttributesW >> 14) & 1;
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v14);
    return 0;
  }
}

```

## disassembly

```asm
0x18001a404  push    rbx
0x18001a406  push    rsi
0x18001a407  push    r12
0x18001a409  push    r13
0x18001a40b  push    r14
0x18001a40d  push    r15
0x18001a40f  sub     rsp, 48h
0x18001a413  mov     r12, rdx
0x18001a416  mov     r14, rcx
0x18001a419  xor     r13d, r13d
0x18001a41c  mov     [rsp+78h+var_50], r13
0x18001a421  mov     [rsp+78h+var_48], r13d
0x18001a426  mov     [rsp+78h+var_58], r13
0x18001a42b  test    rcx, rcx
0x18001a42e  jz      short loc_18001A447
0x18001a430  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001a434  mov     rax, rbx
0x18001a437  inc     rax
0x18001a43a  cmp     [rcx+rax*2], r13w
0x18001a43f  jnz     short loc_18001A437
0x18001a441  cmp     rax, 1
0x18001a445  jnb     short loc_18001A47F
0x18001a447  lea     rsi, WPP_GLOBAL_Control
0x18001a44e  mov     ebx, 57h ; 'W'
0x18001a453  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a45a  cmp     rcx, rsi
0x18001a45d  jnz     loc_18001A605
0x18001a463  lea     rcx, [rsp+78h+var_58]
0x18001a468  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001a46d  nop
0x18001a46e  mov     eax, ebx
0x18001a470  add     rsp, 48h
0x18001a474  pop     r15
0x18001a476  pop     r14
0x18001a478  pop     r13
0x18001a47a  pop     r12
0x18001a47c  pop     rsi
0x18001a47d  pop     rbx
0x18001a47e  retn
0x18001a47f  call    cs:__imp_GetFileAttributesW
0x18001a485  cmp     eax, 0FFFFFFFFh
0x18001a488  jz      loc_18001A510
0x18001a48e  shr     eax, 0Eh
0x18001a491  and     eax, 1
0x18001a494  mov     [r12], eax
0x18001a498  lea     rcx, [rsp+78h+var_58]
0x18001a49d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001a4a2  nop
0x18001a4a3  xor     eax, eax
0x18001a4a5  jmp     short loc_18001A470
0x18001a4a7  lea     edx, [rbx+1]
0x18001a4aa  add     rdx, rdx; uBytes
0x18001a4ad  mov     ecx, 40h ; '@'; uFlags
0x18001a4b2  call    cs:__imp_LocalAlloc
0x18001a4b8  mov     r15, rax
0x18001a4bb  mov     [rsp+78h+var_50], rax
0x18001a4c0  test    rax, rax
0x18001a4c3  jz      loc_18001A59D
0x18001a4c9  mov     r8d, ebx
0x18001a4cc  add     r8, r8; Size
0x18001a4cf  mov     rdx, r14; Src
0x18001a4d2  mov     rcx, rax; void *
0x18001a4d5  call    memcpy_0
0x18001a4da  mov     rcx, r15; lpFileName
0x18001a4dd  call    cs:__imp_GetFileAttributesW
0x18001a4e3  cmp     eax, 0FFFFFFFFh
0x18001a4e6  jnz     short loc_18001A48E
0x18001a4e8  call    cs:__imp_GetLastError
0x18001a4ee  mov     ebx, eax
0x18001a4f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a4f7  cmp     rcx, rsi
0x18001a4fa  jnz     loc_18001A5DE
0x18001a500  lea     rcx, [rsp+78h+var_58]
0x18001a505  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001a50a  nop
0x18001a50b  jmp     loc_18001A46E
0x18001a510  lea     rsi, WPP_GLOBAL_Control
0x18001a517  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a51e  cmp     rcx, rsi
0x18001a521  jz      short loc_18001A545
0x18001a523  test    byte ptr [rcx+1Ch], 2
0x18001a527  jz      short loc_18001A545
0x18001a529  mov     edx, 0Bh
0x18001a52e  lea     r8, WPP_e65014c76418321bb93a76a498c7a7da_Traceguids
0x18001a535  mov     rcx, [rcx+10h]
0x18001a539  call    WPP_SF_
0x18001a53e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a545  inc     rbx
0x18001a548  cmp     [r14+rbx*2], r13w
0x18001a54d  jnz     short loc_18001A545
0x18001a54f  dec     ebx
0x18001a551  jmp     short loc_18001A561
0x18001a553  cmp     word ptr [r14+rbx*2], 5Ch ; '\'
0x18001a559  jz      loc_18001A4A7
0x18001a55f  dec     ebx
0x18001a561  cmp     ebx, 1
0x18001a564  jge     short loc_18001A553
0x18001a566  mov     ebx, 57h ; 'W'
0x18001a56b  cmp     rcx, rsi
0x18001a56e  jz      short loc_18001A58D
0x18001a570  test    byte ptr [rcx+1Ch], 2
0x18001a574  jz      short loc_18001A58D
0x18001a576  lea     edx, [rbx-4Bh]
0x18001a579  mov     r9d, ebx
0x18001a57c  lea     r8, WPP_e65014c76418321bb93a76a498c7a7da_Traceguids
0x18001a583  mov     rcx, [rcx+10h]
0x18001a587  call    WPP_SF_d
0x18001a58c  nop
0x18001a58d  lea     rcx, [rsp+78h+var_58]
0x18001a592  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001a597  nop
0x18001a598  jmp     loc_18001A46E
0x18001a59d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5a4  cmp     rcx, rsi
0x18001a5a7  jz      short loc_18001A5C9
0x18001a5a9  test    byte ptr [rcx+1Ch], 2
0x18001a5ad  jz      short loc_18001A5C9
0x18001a5af  mov     edx, 0Dh
0x18001a5b4  lea     r9d, [rdx+1]
0x18001a5b8  lea     r8, WPP_e65014c76418321bb93a76a498c7a7da_Traceguids
0x18001a5bf  mov     rcx, [rcx+10h]
0x18001a5c3  call    WPP_SF_d
0x18001a5c8  nop
0x18001a5c9  lea     rcx, [rsp+78h+var_58]
0x18001a5ce  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001a5d3  nop
0x18001a5d4  mov     eax, 0Eh
0x18001a5d9  jmp     loc_18001A470
0x18001a5de  test    byte ptr [rcx+1Ch], 2
0x18001a5e2  jz      loc_18001A500
0x18001a5e8  mov     edx, 0Eh
0x18001a5ed  mov     r9d, ebx
0x18001a5f0  lea     r8, WPP_e65014c76418321bb93a76a498c7a7da_Traceguids
0x18001a5f7  mov     rcx, [rcx+10h]
0x18001a5fb  call    WPP_SF_d
0x18001a600  jmp     loc_18001A500
0x18001a605  test    byte ptr [rcx+1Ch], 2
0x18001a609  jz      loc_18001A463
0x18001a60f  mov     edx, 0Ah
0x18001a614  mov     r9d, ebx
0x18001a617  lea     r8, WPP_e65014c76418321bb93a76a498c7a7da_Traceguids
0x18001a61e  mov     rcx, [rcx+10h]
0x18001a622  call    WPP_SF_d
0x18001a627  jmp     loc_18001A463
```
