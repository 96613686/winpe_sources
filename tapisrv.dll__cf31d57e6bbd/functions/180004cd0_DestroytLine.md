# DestroytLine

- ea: `0x180004cd0`
- end: `0x180004fc5`
- name: `DestroytLine`
- size: `757`
- prototype: `__int64 __fastcall(_DWORD *, int)`
- caller_count: `3`
- callee_count: `14`
- tags: ``

## callers

- `0x180005378`
- `0x180017be0`
- `0x18001fb28`

## callees

- `0x180001f50`
- `0x18000469c`
- `0x180004cd0`
- `0x180005378`
- `0x180006dec`
- `0x180006f24`
- `0x18001f6c4`
- `0x18002ba2c`
- `0x18002c8d4`
- `0x18002f778`
- `0x1800342d4`
- `0x18003dc84`
- `0x18003e15c`
- `0x180040010`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x180004ea6`
- `KERNEL32!ReleaseMutex` at `0x180004eea`
- `KERNEL32!ReleaseMutex` at `0x180004f32`
- `KERNEL32!ReleaseMutex` at `0x180004ea6`
- `KERNEL32!ReleaseMutex` at `0x180004eea`
- `KERNEL32!ReleaseMutex` at `0x180004f32`
- `KERNEL32!WaitForSingleObject` at `0x180004e8b`
- `KERNEL32!WaitForSingleObject` at `0x180004ed5`
- `KERNEL32!WaitForSingleObject` at `0x180004f09`
- `KERNEL32!WaitForSingleObject` at `0x180004e8b`
- `KERNEL32!WaitForSingleObject` at `0x180004ed5`
- `KERNEL32!WaitForSingleObject` at `0x180004f09`

## string_xrefs

- `0x180004f63`: `DestroytLine: WaitForExclusivetLineAccess failed`

## pseudocode

```c
__int64 __fastcall DestroytLine(_DWORD *a1, int a2)
{
  int v4; // esi
  __int64 i; // rsi
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned __int64 v9; // r14
  HANDLE v10; // rcx
  __int64 v11; // r14
  __int64 v12; // r14
  __int64 v13; // r15
  void (__fastcall *v14)(_QWORD); // rax
  __int64 LineLookupEntry; // rax
  __int64 v16; // rcx
  LPVOID lpMem; // [rsp+20h] [rbp-98h] BYREF
  __int128 v18; // [rsp+28h] [rbp-90h] BYREF
  __int128 v19; // [rsp+38h] [rbp-80h]
  __int64 v20; // [rsp+48h] [rbp-70h]
  _DWORD v21[26]; // [rsp+50h] [rbp-68h] BYREF
  unsigned int v22; // [rsp+D0h] [rbp+18h] BYREF
  HANDLE hMutex; // [rsp+D8h] [rbp+20h] BYREF

  v22 = 0;
  hMutex = 0;
  TRACELogPrint(524290, "DestroytLine: enter, ptLine=x%p, bUnconditional=%d", a1, a2);
  if ( (unsigned int)WaitForExclusivetLineAccess(a1, &hMutex, &v22) )
  {
    v21[1] = 0;
    memset_0(v21, 0, 0x44u);
    lpMem = v21;
    if ( *a1 == 1162758476 && (a2 == 1 || !*((_QWORD *)a1 + 2)) )
    {
      if ( (unsigned int)GetLineClientListFromLine(a1, &lpMem) )
      {
        lpMem = v21;
        v21[0] = 8;
      }
      *a1 = 1280724553;
      v4 = 0;
    }
    else
    {
      v4 = 1;
    }
    MyReleaseMutex(hMutex, v22);
    if ( v4 )
      return TRACELogPrint(524290, "DestroytLine: exit, didn't destroy tLine=x%p", a1);
    if ( *(_DWORD *)lpMem )
    {
      v18 = 0;
      v19 = 0;
      v20 = 0;
      LODWORD(v18) = 40;
      LODWORD(v19) = 3;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v22 = i;
        if ( (unsigned int)i >= *(_DWORD *)lpMem )
          break;
        v7 = *((_QWORD *)lpMem + i + 1);
        v8 = *(_QWORD *)(v7 + 16);
        DWORD1(v18) = *(_DWORD *)(v8 + 28);
        HIDWORD(v18) = *(_DWORD *)(v7 + 56);
        DWORD1(v19) = *(_DWORD *)(v7 + 72);
        if ( *(_DWORD *)v7 == 1229734732 )
        {
          v9 = *(_QWORD *)(v7 + 8);
          if ( !(unsigned int)FMsgDisabled(*(unsigned int *)(v8 + 48), v7 + 168, 3) )
            WriteEventBuffer(v9, (unsigned int *)&v18);
        }
      }
    }
    if ( lpMem != v21 )
      ServerFree(lpMem);
    v10 = (HANDLE)*((_QWORD *)a1 + 1);
    for ( hMutex = v10; ; v10 = hMutex )
    {
      WaitForSingleObject(v10, 0xFFFFFFFF);
      v11 = *((_QWORD *)a1 + 2);
      if ( v11 )
        LODWORD(v11) = *(_DWORD *)(v11 + 24);
      ReleaseMutex(hMutex);
      if ( !(_DWORD)v11 )
        break;
      DestroytLineClient((unsigned int)v11);
    }
    while ( 1 )
    {
      WaitForSingleObject(hMutex, 0xFFFFFFFF);
      v12 = *((_QWORD *)a1 + 31);
      ReleaseMutex(hMutex);
      if ( !v12 )
        break;
      DestroytCall(v12);
    }
    v13 = *((_QWORD *)a1 + 24);
    if ( (*(_BYTE *)(v13 + 24) & 1) != 0 )
      WaitForSingleObject(*(HANDLE *)(v13 + 8), 0xFFFFFFFF);
    v14 = *(void (__fastcall **)(_QWORD))(v13 + 168);
    if ( v14 )
      v14(*((_QWORD *)a1 + 25));
    if ( (*(_BYTE *)(v13 + 24) & 1) != 0 )
      ReleaseMutex(*(HANDLE *)(v13 + 8));
    LineLookupEntry = GetLineLookupEntry((unsigned int)a1[53]);
    if ( LineLookupEntry )
      *(_QWORD *)(LineLookupEntry + 8) = 0;
    DereferenceObject(v16, a1[52], 1);
  }
  else
  {
    TRACELogPrint(65538, "DestroytLine: WaitForExclusivetLineAccess failed");
  }
  if ( dword_1800518AC )
    --dword_1800518AC;
  else
    TRACELogPrint(262146, "PERF: dwNumLinesInUse below 0");
  return TRACELogPrint(524290, "DestroytLine: exit, destroyed line=x%p", a1);
}

```

## disassembly

```asm
0x180004cd0  mov     rax, rsp
0x180004cd3  mov     [rax+10h], rsi
0x180004cd7  mov     [rax+8], rcx
0x180004cdb  push    rdi
0x180004cdc  push    r14
0x180004cde  push    r15
0x180004ce0  sub     rsp, 0A0h
0x180004ce7  mov     esi, edx
0x180004ce9  mov     rdi, rcx
0x180004cec  mov     dword ptr [rax+18h], 0
0x180004cf3  mov     qword ptr [rax+20h], 0
0x180004cfb  mov     r9d, edx
0x180004cfe  mov     r8, rcx
0x180004d01  lea     rdx, aDestroytlineEn; "DestroytLine: enter, ptLine=x%p, bUncon"...
0x180004d08  mov     ecx, 80002h
0x180004d0d  call    TRACELogPrint
0x180004d12  lea     r8, [rsp+0B8h+arg_10]
0x180004d1a  lea     rdx, [rsp+0B8h+hMutex]
0x180004d22  mov     rcx, rdi
0x180004d25  call    WaitForExclusivetLineAccess
0x180004d2a  test    eax, eax
0x180004d2c  jz      loc_180004F63
0x180004d32  xor     eax, eax
0x180004d34  mov     [rsp+0B8h+var_64], eax
0x180004d38  xor     edx, edx; Val
0x180004d3a  lea     r8d, [rax+44h]; Size
0x180004d3e  lea     rcx, [rsp+0B8h+var_68]; void *
0x180004d43  call    memset_0
0x180004d48  lea     rax, [rsp+0B8h+var_68]
0x180004d4d  mov     [rsp+0B8h+lpMem], rax
0x180004d52  cmp     dword ptr [rdi], 454E494Ch
0x180004d58  jnz     short loc_180004D93
0x180004d5a  cmp     esi, 1
0x180004d5d  jz      short loc_180004D66
0x180004d5f  cmp     qword ptr [rdi+10h], 0
0x180004d64  jnz     short loc_180004D93
0x180004d66  lea     rdx, [rsp+0B8h+lpMem]
0x180004d6b  mov     rcx, rdi
0x180004d6e  call    GetLineClientListFromLine
0x180004d73  test    eax, eax
0x180004d75  jz      short loc_180004D89
0x180004d77  lea     rax, [rsp+0B8h+var_68]
0x180004d7c  mov     [rsp+0B8h+lpMem], rax
0x180004d81  mov     [rsp+0B8h+var_68], 8
0x180004d89  mov     dword ptr [rdi], 4C564E49h
0x180004d8f  xor     esi, esi
0x180004d91  jmp     short loc_180004D98
0x180004d93  mov     esi, 1
0x180004d98  mov     edx, [rsp+0B8h+arg_10]
0x180004d9f  mov     rcx, [rsp+0B8h+hMutex]
0x180004da7  call    MyReleaseMutex
0x180004dac  test    esi, esi
0x180004dae  jz      short loc_180004DBC
0x180004db0  lea     rdx, aDestroytlineEx; "DestroytLine: exit, didn't destroy tLin"...
0x180004db7  jmp     loc_180004FA3
0x180004dbc  mov     rax, [rsp+0B8h+lpMem]
0x180004dc1  cmp     dword ptr [rax], 0
0x180004dc4  jz      loc_180004E66
0x180004dca  xorps   xmm0, xmm0
0x180004dcd  xor     eax, eax
0x180004dcf  movups  [rsp+0B8h+var_90], xmm0
0x180004dd4  movups  [rsp+0B8h+var_80], xmm0
0x180004dd9  mov     [rsp+0B8h+var_70], rax
0x180004dde  mov     dword ptr [rsp+0B8h+var_90], 28h ; '('
0x180004de6  mov     dword ptr [rsp+0B8h+var_80], 3
0x180004dee  xor     esi, esi
0x180004df0  mov     [rsp+0B8h+arg_10], esi
0x180004df7  mov     rcx, [rsp+0B8h+lpMem]
0x180004dfc  cmp     esi, [rcx]
0x180004dfe  jnb     short loc_180004E66
0x180004e00  mov     rdx, [rcx+rsi*8+8]
0x180004e05  mov     rcx, [rdx+10h]
0x180004e09  mov     eax, [rcx+1Ch]
0x180004e0c  mov     dword ptr [rsp+0B8h+var_90+4], eax
0x180004e10  mov     eax, [rdx+38h]
0x180004e13  mov     dword ptr [rsp+0B8h+var_90+0Ch], eax
0x180004e17  mov     eax, [rdx+48h]
0x180004e1a  mov     dword ptr [rsp+0B8h+var_80+4], eax
0x180004e1e  cmp     dword ptr [rdx], 494C434Ch
0x180004e24  jnz     short loc_180004E51
0x180004e26  mov     r14, [rdx+8]
0x180004e2a  add     rdx, 0A8h
0x180004e31  xor     r9d, r9d
0x180004e34  lea     r8d, [r9+3]
0x180004e38  mov     ecx, [rcx+30h]
0x180004e3b  call    FMsgDisabled
0x180004e40  test    eax, eax
0x180004e42  jnz     short loc_180004E51
0x180004e44  lea     rdx, [rsp+0B8h+var_90]
0x180004e49  mov     rcx, r14
0x180004e4c  call    WriteEventBuffer
0x180004e51  jmp     short loc_180004E62
0x180004e53  mov     rdi, [rsp+0B8h+arg_0]
0x180004e5b  mov     esi, [rsp+0B8h+arg_10]
0x180004e62  inc     esi
0x180004e64  jmp     short loc_180004DF0
0x180004e66  lea     rax, [rsp+0B8h+var_68]
0x180004e6b  mov     rcx, [rsp+0B8h+lpMem]; lpMem
0x180004e70  cmp     rcx, rax
0x180004e73  jz      short loc_180004E7A
0x180004e75  call    ServerFree
0x180004e7a  mov     rcx, [rdi+8]; hHandle
0x180004e7e  mov     [rsp+0B8h+hMutex], rcx
0x180004e86  or      esi, 0FFFFFFFFh
0x180004e89  mov     edx, esi; dwMilliseconds
0x180004e8b  call    cs:__imp_WaitForSingleObject
0x180004e91  mov     r14, [rdi+10h]
0x180004e95  test    r14, r14
0x180004e98  jz      short loc_180004E9E
0x180004e9a  mov     r14d, [r14+18h]
0x180004e9e  mov     rcx, [rsp+0B8h+hMutex]; hMutex
0x180004ea6  call    cs:__imp_ReleaseMutex
0x180004eac  test    r14d, r14d
0x180004eaf  jz      short loc_180004ECB
0x180004eb1  mov     ecx, r14d
0x180004eb4  call    DestroytLineClient
0x180004eb9  mov     rcx, [rsp+0B8h+hMutex]
0x180004ec1  jmp     short loc_180004E89
0x180004ec3  mov     rcx, r14
0x180004ec6  call    DestroytCall
0x180004ecb  mov     edx, esi; dwMilliseconds
0x180004ecd  mov     rcx, [rsp+0B8h+hMutex]; hHandle
0x180004ed5  call    cs:__imp_WaitForSingleObject
0x180004edb  mov     r14, [rdi+0F8h]
0x180004ee2  mov     rcx, [rsp+0B8h+hMutex]; hMutex
0x180004eea  call    cs:__imp_ReleaseMutex
0x180004ef0  test    r14, r14
0x180004ef3  jnz     short loc_180004EC3
0x180004ef5  mov     r15, [rdi+0C0h]
0x180004efc  test    byte ptr [r15+18h], 1
0x180004f01  jz      short loc_180004F0F
0x180004f03  mov     edx, esi; dwMilliseconds
0x180004f05  mov     rcx, [r15+8]; hHandle
0x180004f09  call    cs:__imp_WaitForSingleObject
0x180004f0f  mov     rax, [r15+0A8h]
0x180004f16  test    rax, rax
0x180004f19  jz      short loc_180004F27
0x180004f1b  mov     rcx, [rdi+0C8h]
0x180004f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f27  test    byte ptr [r15+18h], 1
0x180004f2c  jz      short loc_180004F38
0x180004f2e  mov     rcx, [r15+8]; hMutex
0x180004f32  call    cs:__imp_ReleaseMutex
0x180004f38  mov     ecx, [rdi+0D4h]
0x180004f3e  call    GetLineLookupEntry
0x180004f43  test    rax, rax
0x180004f46  jz      short loc_180004F50
0x180004f48  mov     qword ptr [rax+8], 0
0x180004f50  mov     r8d, 1
0x180004f56  mov     edx, [rdi+0D0h]
0x180004f5c  call    DereferenceObject
0x180004f61  jmp     short loc_180004F77
0x180004f63  lea     rdx, aDestroytlineWa; "DestroytLine: WaitForExclusivetLineAcce"...
0x180004f6a  mov     ecx, 10002h
0x180004f6f  call    TRACELogPrint
0x180004f74  or      esi, 0FFFFFFFFh
0x180004f77  mov     eax, cs:dword_1800518AC
0x180004f7d  test    eax, eax
0x180004f7f  jz      short loc_180004F8B
0x180004f81  add     eax, esi
0x180004f83  mov     cs:dword_1800518AC, eax
0x180004f89  jmp     short loc_180004F9C
0x180004f8b  lea     rdx, aPerfDwnumlines; "PERF: dwNumLinesInUse below 0"
0x180004f92  mov     ecx, 40002h
0x180004f97  call    TRACELogPrint
0x180004f9c  lea     rdx, aDestroytlineEx_0; "DestroytLine: exit, destroyed line=x%p"
0x180004fa3  mov     r8, rdi
0x180004fa6  mov     ecx, 80002h
0x180004fab  call    TRACELogPrint
0x180004fb0  mov     rsi, [rsp+0B8h+arg_8]
0x180004fb8  add     rsp, 0A0h
0x180004fbf  pop     r15
0x180004fc1  pop     r14
0x180004fc3  pop     rdi
0x180004fc4  retn
```
