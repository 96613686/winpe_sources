# SeqDestruct

- ea: `0x180002d14`
- end: `0x180002f54`
- name: `SeqDestruct`
- size: `576`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `5`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180002958`
- `0x18000a6b8`
- `0x18000a8f0`
- `0x18000b3fc`
- `0x18000b860`

## callees

- `0x180002250`
- `0x180002280`
- `0x1800022bc`
- `0x180002d14`
- `0x180009a48`
- `0x18000a624`
- `0x18001dc70`
- `0x180021f44`
- `0x180021ff0`
- `0x1800224f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e4b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002d36`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002d36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002dc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002eec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002dc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002eec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f04`

## string_xrefs

- `0x180002d58`: `DeleteCriticalSection for pExecQueue->csLock;`

## pseudocode

```c
void __fastcall SeqDestruct(char *lpMem)
{
  DWORD LastError; // ebx
  int v3; // eax
  void *v4; // rcx
  int i; // eax
  void *v6; // rcx
  void *v7; // rcx
  DWORD v8; // ebx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  struct CONTENTS_FILE *v16; // rcx
  __int128 v17; // [rsp+60h] [rbp-48h] BYREF
  __int64 v18; // [rsp+70h] [rbp-38h]
  LPCWSTR lpModuleName; // [rsp+A8h] [rbp+0h]

  if ( lpMem )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(lpMem + 184));
    LastError = GetLastError();
    v3 = (unsigned int)ConstructPartialMsgW(0x4000000u, "DeleteCriticalSection for pExecQueue->csLock;");
    WdsSetupLogMessageW(
      v3,
      589824,
      (int)L"D",
      0,
      1992,
      L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
      (__int64)L"SeqDestruct",
      lpModuleName,
      LastError,
      0,
      0);
    v4 = (void *)*((_QWORD *)lpMem + 21);
    if ( v4 )
      CloseHandle(v4);
    if ( *((_QWORD *)lpMem + 16) )
    {
      v17 = 0;
      v18 = 0;
      for ( i = EnumFirstHashTableStringW(&v17); i; i = EnumNextHashTableStringW(&v17) )
        DestructList(**((LPVOID **)&v17 + 1));
      HtFree(*((_QWORD *)lpMem + 16));
    }
    v6 = (void *)*((_QWORD *)lpMem + 7);
    if ( v6 )
      DestructList(v6);
    v7 = (void *)*((_QWORD *)lpMem + 9);
    if ( v7 )
      DestructList(v7);
    if ( *((_QWORD *)lpMem + 5) )
    {
      v8 = GetLastError();
      v9 = (unsigned int)ConstructPartialMsgW(0x4000081u, "Destroying any unreferenced modules! (SEQ6)");
      WdsSetupLogMessageW(
        v9,
        589824,
        (int)L"D",
        0,
        2027,
        L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
        (__int64)L"SeqDestruct",
        lpModuleName,
        v8,
        0,
        0);
      DestructList(*((LPVOID *)lpMem + 5));
    }
    v10 = *((_QWORD *)lpMem + 8);
    if ( v10 )
      HtFree(v10);
    v11 = *((_QWORD *)lpMem + 10);
    if ( v11 )
      HtFree(v11);
    v12 = *((_QWORD *)lpMem + 12);
    if ( v12 )
      HtFree(v12);
    v13 = (void *)*((_QWORD *)lpMem + 30);
    if ( v13 )
      CloseHandle(v13);
    v14 = (void *)*((_QWORD *)lpMem + 31);
    if ( v14 )
      CloseHandle(v14);
    v15 = (void *)*((_QWORD *)lpMem + 28);
    if ( v15 )
      DestructList(v15);
    SC_Destruct(lpMem + 104);
    v16 = (struct CONTENTS_FILE *)*((_QWORD *)lpMem + 33);
    if ( v16 )
      pDestructContentsFile(v16);
    WdsSeqFree(lpMem);
  }
}

```

## disassembly

```asm
0x180002d14  push    rbx
0x180002d16  push    rsi
0x180002d17  push    rdi
0x180002d18  push    r12
0x180002d1a  push    r13
0x180002d1c  sub     rsp, 80h
0x180002d23  mov     rsi, rcx
0x180002d26  test    rcx, rcx
0x180002d29  jz      loc_180002F44
0x180002d2f  add     rcx, 0B8h; lpCriticalSection
0x180002d36  call    cs:__imp_DeleteCriticalSection
0x180002d3d  nop     dword ptr [rax+rax+00h]
0x180002d42  mov     rdi, [rsp+0A8h]
0x180002d4a  call    cs:__imp_GetLastError
0x180002d51  nop     dword ptr [rax+rax+00h]
0x180002d56  mov     ebx, eax
0x180002d58  lea     rdx, aDeletecritical; "DeleteCriticalSection for pExecQueue->c"...
0x180002d5f  mov     ecx, 4000000h; unsigned int
0x180002d64  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180002d69  mov     rcx, rax; int
0x180002d6c  mov     [rsp+0A8h+var_58], 0; int
0x180002d74  mov     [rsp+0A8h+var_60], 0; __int64
0x180002d7d  mov     [rsp+0A8h+var_68], ebx; int
0x180002d81  mov     [rsp+0A8h+lpModuleName], rdi; lpModuleName
0x180002d86  lea     r12, aSeqdestruct; "SeqDestruct"
0x180002d8d  mov     [rsp+0A8h+var_78], r12; __int64
0x180002d92  lea     r13, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180002d99  mov     [rsp+0A8h+var_80], r13; unsigned __int16 *
0x180002d9e  mov     [rsp+0A8h+var_88], 7C8h; int
0x180002da6  xor     r9d, r9d; int
0x180002da9  lea     r8, aD_1; "D"
0x180002db0  mov     edx, 90000h; int
0x180002db5  call    WdsSetupLogMessageW
0x180002dba  mov     rcx, [rsi+0A8h]; hObject
0x180002dc1  test    rcx, rcx
0x180002dc4  jz      short loc_180002DD2
0x180002dc6  call    cs:__imp_CloseHandle
0x180002dcd  nop     dword ptr [rax+rax+00h]
0x180002dd2  mov     rdx, [rsi+80h]
0x180002dd9  test    rdx, rdx
0x180002ddc  jz      short loc_180002E20
0x180002dde  xorps   xmm0, xmm0
0x180002de1  xor     eax, eax
0x180002de3  movups  [rsp+0A8h+var_48], xmm0
0x180002de8  mov     [rsp+0A8h+var_38], rax
0x180002ded  lea     rcx, [rsp+0A8h+var_48]
0x180002df2  call    EnumFirstHashTableStringW
0x180002df7  jmp     short loc_180002E10
0x180002df9  mov     rcx, qword ptr [rsp+0A8h+var_48+8]
0x180002dfe  mov     rcx, [rcx]; lpMem
0x180002e01  call    DestructList
0x180002e06  lea     rcx, [rsp+0A8h+var_48]
0x180002e0b  call    EnumNextHashTableStringW
0x180002e10  test    eax, eax
0x180002e12  jnz     short loc_180002DF9
0x180002e14  mov     rcx, [rsi+80h]
0x180002e1b  call    HtFree
0x180002e20  mov     rcx, [rsi+38h]; lpMem
0x180002e24  test    rcx, rcx
0x180002e27  jz      short loc_180002E2E
0x180002e29  call    DestructList
0x180002e2e  mov     rcx, [rsi+48h]; lpMem
0x180002e32  test    rcx, rcx
0x180002e35  jz      short loc_180002E3C
0x180002e37  call    DestructList
0x180002e3c  cmp     qword ptr [rsi+28h], 0
0x180002e41  jz      short loc_180002EB6
0x180002e43  mov     rdi, [rsp+0A8h]
0x180002e4b  call    cs:__imp_GetLastError
0x180002e52  nop     dword ptr [rax+rax+00h]
0x180002e57  mov     ebx, eax
0x180002e59  lea     rdx, aDestroyingAnyU; "Destroying any unreferenced modules! (S"...
0x180002e60  mov     ecx, 4000081h; unsigned int
0x180002e65  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180002e6a  mov     rcx, rax; int
0x180002e6d  mov     [rsp+0A8h+var_58], 0; int
0x180002e75  mov     [rsp+0A8h+var_60], 0; __int64
0x180002e7e  mov     [rsp+0A8h+var_68], ebx; int
0x180002e82  mov     [rsp+0A8h+lpModuleName], rdi; lpModuleName
0x180002e87  mov     [rsp+0A8h+var_78], r12; __int64
0x180002e8c  mov     [rsp+0A8h+var_80], r13; unsigned __int16 *
0x180002e91  mov     [rsp+0A8h+var_88], 7EBh; int
0x180002e99  xor     r9d, r9d; int
0x180002e9c  lea     r8, aD_1; "D"
0x180002ea3  mov     edx, 90000h; int
0x180002ea8  call    WdsSetupLogMessageW
0x180002ead  mov     rcx, [rsi+28h]; lpMem
0x180002eb1  call    DestructList
0x180002eb6  mov     rcx, [rsi+40h]
0x180002eba  test    rcx, rcx
0x180002ebd  jz      short loc_180002EC4
0x180002ebf  call    HtFree
0x180002ec4  mov     rcx, [rsi+50h]
0x180002ec8  test    rcx, rcx
0x180002ecb  jz      short loc_180002ED2
0x180002ecd  call    HtFree
0x180002ed2  mov     rcx, [rsi+60h]
0x180002ed6  test    rcx, rcx
0x180002ed9  jz      short loc_180002EE0
0x180002edb  call    HtFree
0x180002ee0  mov     rcx, [rsi+0F0h]; hObject
0x180002ee7  test    rcx, rcx
0x180002eea  jz      short loc_180002EF8
0x180002eec  call    cs:__imp_CloseHandle
0x180002ef3  nop     dword ptr [rax+rax+00h]
0x180002ef8  mov     rcx, [rsi+0F8h]; hObject
0x180002eff  test    rcx, rcx
0x180002f02  jz      short loc_180002F10
0x180002f04  call    cs:__imp_CloseHandle
0x180002f0b  nop     dword ptr [rax+rax+00h]
0x180002f10  mov     rcx, [rsi+0E0h]; lpMem
0x180002f17  test    rcx, rcx
0x180002f1a  jz      short loc_180002F21
0x180002f1c  call    DestructList
0x180002f21  lea     rcx, [rsi+68h]
0x180002f25  call    SC_Destruct
0x180002f2a  mov     rcx, [rsi+108h]; struct CONTENTS_FILE *
0x180002f31  test    rcx, rcx
0x180002f34  jz      short loc_180002F3B
0x180002f36  call    ?pDestructContentsFile@@YAXPEAUCONTENTS_FILE@@@Z; pDestructContentsFile(CONTENTS_FILE *)
0x180002f3b  mov     rcx, rsi; lpMem
0x180002f3e  call    WdsSeqFree
0x180002f43  nop
0x180002f44  add     rsp, 80h
0x180002f4b  pop     r13
0x180002f4d  pop     r12
0x180002f4f  pop     rdi
0x180002f50  pop     rsi
0x180002f51  pop     rbx
0x180002f52  retn
0x180027ab6  push    rbp
0x180027ab8  sub     rsp, 60h
0x180027abc  mov     rbp, rdx
0x180027abf  add     rsp, 60h
0x180027ac3  pop     rbp
0x180027ac4  retn
```
