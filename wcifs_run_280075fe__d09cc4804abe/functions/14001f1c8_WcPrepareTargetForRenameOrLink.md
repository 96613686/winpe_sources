# WcPrepareTargetForRenameOrLink

- ea: `0x14001f1c8`
- end: `0x14001f480`
- name: `WcPrepareTargetForRenameOrLink`
- size: `696`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x14001f08c`

## callees

- `0x1400016f0`
- `0x1400020c4`
- `0x140004198`
- `0x140007c60`
- `0x1400080c0`
- `0x14001c244`
- `0x14001ecb8`
- `0x14001f1c8`
- `0x14002ee54`

## import_xrefs

- `FLTMGR!FltQueryInformationByName` at `0x14001f2a1`
- `FLTMGR!FltQueryInformationByName` at `0x14001f2a1`

## pseudocode

```c
__int64 __fastcall WcPrepareTargetForRenameOrLink(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        __int64 a3,
        void *a4,
        UNICODE_STRING *a5)
{
  __int64 v9; // rcx
  int v10; // eax
  _BYTE *v11; // rax
  char v12; // di
  int v13; // edx
  int IsTargetPartialDirectory; // ebx
  int v15; // edx
  __int64 UnionContext; // rdi
  int v17; // edx
  __int64 v19; // [rsp+38h] [rbp-A9h]
  __int64 v20; // [rsp+40h] [rbp-A1h] BYREF
  _BYTE v21[48]; // [rsp+48h] [rbp-99h] BYREF
  __int128 v22; // [rsp+78h] [rbp-69h] BYREF
  _DWORD v23[20]; // [rsp+90h] [rbp-51h] BYREF

  memset(v21, 0, 44);
  v22 = 0;
  memset(v23, 0, 0x48u);
  v9 = *(_QWORD *)(a1 + 16);
  LOBYTE(v20) = 0;
  v10 = *(_DWORD *)(v9 + 32);
  if ( v10 != 10 && v10 != 65 || (v11 = *(_BYTE **)(v9 + 56), !*v11) || (v12 = 1, (*(_DWORD *)v11 & 2) == 0) )
    v12 = 0;
  *(_DWORD *)v21 = 48;
  *(_QWORD *)&v21[8] = a4;
  *(_DWORD *)&v21[24] = 512;
  *(_QWORD *)&v21[16] = a5;
  *(_OWORD *)&v21[32] = 0;
  IsTargetPartialDirectory = ((__int64 (__fastcall *)(PFLT_FILTER, struct _FLT_INSTANCE *, _BYTE *, __int128 *, _DWORD *, int, int, _QWORD, __int64))FltQueryInformationByName)(
                               Globals,
                               a2,
                               v21,
                               &v22,
                               v23,
                               72,
                               68,
                               0,
                               v20);
  if ( IsTargetPartialDirectory == -1073741772 )
  {
    return 0;
  }
  else if ( IsTargetPartialDirectory >= 0 )
  {
    if ( v23[15] == -1610612705 )
    {
      return (unsigned int)WcDeleteTombstone(a1, a2, *(struct _FILE_OBJECT **)(*(_QWORD *)(a1 + 16) + 40LL), a4, a5);
    }
    else if ( v12 && (v23[14] & 0x10) != 0 )
    {
      UnionContext = WcGetUnionContext(a1, a2, a3);
      if ( UnionContext )
      {
        IsTargetPartialDirectory = WcIsTargetPartialDirectory(a2, (__int64)a4, (__int64)&v20);
        if ( IsTargetPartialDirectory >= 0 )
        {
          if ( (_BYTE)v20 )
          {
            IsTargetPartialDirectory = -1073741567;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
              {
                LODWORD(v19) = -1073741567;
                LOBYTE(v17) = 5;
                WPP_RECORDER_SF_sDd(
                  WcVerboseRecorder,
                  v17,
                  13,
                  199,
                  (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
                  (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
                  55,
                  v19);
              }
            }
          }
        }
        WcReleaseUnionContext(UnionContext);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = 3;
          WPP_RECORDER_SF_sD(
            WPP_GLOBAL_Control->DeviceExtension,
            v15,
            13,
            198,
            (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
            28);
        }
        return 0;
      }
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v19) = IsTargetPartialDirectory;
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      13,
      197,
      (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
      4,
      v19);
  }
  return (unsigned int)IsTargetPartialDirectory;
}

```

## disassembly

```asm
0x14001f1c8  push    rbp
0x14001f1ca  push    rbx
0x14001f1cb  push    rsi
0x14001f1cc  push    rdi
0x14001f1cd  push    r12
0x14001f1cf  push    r13
0x14001f1d1  push    r14
0x14001f1d3  push    r15
0x14001f1d5  lea     rbp, [rsp-17h]
0x14001f1da  sub     rsp, 0F8h
0x14001f1e1  mov     rax, cs:__security_cookie
0x14001f1e8  xor     rax, rsp
0x14001f1eb  mov     [rbp+4Fh+var_50], rax
0x14001f1ef  mov     r12, [rbp+4Fh+arg_20]
0x14001f1f3  xorps   xmm0, xmm0
0x14001f1f6  xor     eax, eax
0x14001f1f8  mov     r13, r8
0x14001f1fb  mov     rsi, rdx
0x14001f1fe  mov     r14, rcx
0x14001f201  movups  [rsp+130h+var_D8], xmm0
0x14001f206  xor     edx, edx; Val
0x14001f208  lea     rcx, [rbp+4Fh+var_A0]; void *
0x14001f20c  lea     ebx, [rax+48h]
0x14001f20f  mov     r15, r9
0x14001f212  mov     r8d, ebx; Size
0x14001f215  movups  [rsp+130h+var_E8], xmm0
0x14001f21a  movups  [rbp+4Fh+var_D8+0Ch], xmm0
0x14001f21e  movups  [rbp+4Fh+var_B8], xmm0
0x14001f222  call    memset
0x14001f227  mov     rcx, [r14+10h]
0x14001f22b  xor     edx, edx
0x14001f22d  mov     byte ptr [rsp+130h+var_F0], dl
0x14001f231  mov     eax, [rcx+20h]
0x14001f234  cmp     eax, 0Ah
0x14001f237  jz      short loc_14001F23E
0x14001f239  cmp     eax, 41h ; 'A'
0x14001f23c  jnz     short loc_14001F24F
0x14001f23e  mov     rax, [rcx+38h]
0x14001f242  cmp     [rax], dl
0x14001f244  jz      short loc_14001F24F
0x14001f246  mov     eax, [rax]
0x14001f248  mov     dil, 1
0x14001f24b  test    al, 2
0x14001f24d  jnz     short loc_14001F252
0x14001f24f  mov     dil, dl
0x14001f252  mov     rcx, cs:Globals
0x14001f259  lea     rax, [rbp+4Fh+var_A0]
0x14001f25d  mov     [rsp+130h+var_F8], rdx
0x14001f262  lea     r9, [rbp+4Fh+var_B8]
0x14001f266  mov     [rsp+130h+var_100], 44h ; 'D'
0x14001f26e  lea     r8, [rsp+130h+var_E8]
0x14001f273  xorps   xmm0, xmm0
0x14001f276  mov     dword ptr [rsp+130h+var_108], ebx
0x14001f27a  mov     rdx, rsi
0x14001f27d  mov     [rsp+130h+var_110], rax
0x14001f282  mov     dword ptr [rsp+130h+var_E8], 30h ; '0'
0x14001f28a  mov     qword ptr [rsp+130h+var_E8+8], r15
0x14001f28f  mov     dword ptr [rsp+130h+var_D8+8], 200h
0x14001f297  mov     qword ptr [rsp+130h+var_D8], r12
0x14001f29c  movdqu  [rbp+4Fh+var_C8], xmm0
0x14001f2a1  call    cs:__imp_FltQueryInformationByName
0x14001f2a8  nop     dword ptr [rax+rax+00h]
0x14001f2ad  mov     ebx, eax
0x14001f2af  cmp     eax, 0C0000034h
0x14001f2b4  jnz     short loc_14001F2BD
0x14001f2b6  xor     ebx, ebx
0x14001f2b8  jmp     loc_14001F45D
0x14001f2bd  test    ebx, ebx
0x14001f2bf  jns     short loc_14001F31C
0x14001f2c1  lea     rax, WPP_RECORDER_INITIALIZED
0x14001f2c8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001f2cf  jz      loc_14001F45D
0x14001f2d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f2dc  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001f2e3  mov     dword ptr [rsp+130h+var_F8], ebx
0x14001f2e7  mov     r9d, 0C5h
0x14001f2ed  mov     [rsp+130h+var_100], 2204h
0x14001f2f5  mov     r8d, 0Dh
0x14001f2fb  mov     [rsp+130h+var_108], rax
0x14001f300  mov     dl, 2
0x14001f302  mov     rcx, [rcx+40h]
0x14001f306  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001f30d  mov     [rsp+130h+var_110], rax
0x14001f312  call    WPP_RECORDER_SF_sDd
0x14001f317  jmp     loc_14001F45D
0x14001f31c  cmp     [rbp+4Fh+var_64], 0A000001Fh
0x14001f323  jnz     short loc_14001F347
0x14001f325  mov     r8, [r14+10h]
0x14001f329  mov     r9, r15
0x14001f32c  mov     rdx, rsi
0x14001f32f  mov     [rsp+130h+var_110], r12
0x14001f334  mov     rcx, r14
0x14001f337  mov     r8, [r8+28h]
0x14001f33b  call    WcDeleteTombstone
0x14001f340  mov     ebx, eax
0x14001f342  jmp     loc_14001F45D
0x14001f347  test    dil, dil
0x14001f34a  jz      loc_14001F45D
0x14001f350  test    [rbp+4Fh+var_68], 10h
0x14001f354  jz      loc_14001F45D
0x14001f35a  mov     r8, r13
0x14001f35d  mov     rdx, rsi
0x14001f360  mov     rcx, r14
0x14001f363  call    WcGetUnionContext
0x14001f368  xor     r14d, r14d
0x14001f36b  mov     rdi, rax
0x14001f36e  test    rax, rax
0x14001f371  jnz     short loc_14001F3C7
0x14001f373  lea     rax, WPP_RECORDER_INITIALIZED
0x14001f37a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001f381  jz      short loc_14001F3BF
0x14001f383  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f38a  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001f391  mov     [rsp+130h+var_100], 221Ch
0x14001f399  lea     r8d, [rdi+0Dh]
0x14001f39d  mov     [rsp+130h+var_108], rax
0x14001f3a2  mov     r9d, 0C6h
0x14001f3a8  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001f3af  mov     dl, 3
0x14001f3b1  mov     rcx, [rcx+40h]
0x14001f3b5  mov     [rsp+130h+var_110], rax
0x14001f3ba  call    WPP_RECORDER_SF_sD
0x14001f3bf  mov     ebx, r14d
0x14001f3c2  jmp     loc_14001F45D
0x14001f3c7  lea     rax, [rsp+130h+var_F0]
0x14001f3cc  mov     r9, r13
0x14001f3cf  mov     [rsp+130h+var_108], rax; __int64
0x14001f3d4  mov     r8, r12
0x14001f3d7  mov     rdx, rdi
0x14001f3da  mov     [rsp+130h+var_110], r15; __int64
0x14001f3df  mov     rcx, rsi; Instance
0x14001f3e2  call    WcIsTargetPartialDirectory
0x14001f3e7  mov     ebx, eax
0x14001f3e9  test    eax, eax
0x14001f3eb  js      short loc_14001F455
0x14001f3ed  cmp     byte ptr [rsp+130h+var_F0], r14b
0x14001f3f2  jz      short loc_14001F455
0x14001f3f4  mov     ebx, 0C0000101h
0x14001f3f9  lea     rax, WPP_RECORDER_INITIALIZED
0x14001f400  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001f407  jz      short loc_14001F455
0x14001f409  mov     rax, cs:WPP_GLOBAL_Control
0x14001f410  cmp     [rax+48h], r14w
0x14001f415  jz      short loc_14001F455
0x14001f417  mov     rcx, cs:_WcVerboseRecorder
0x14001f41e  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001f425  mov     dword ptr [rsp+130h+var_F8], ebx
0x14001f429  mov     r9d, 0C7h
0x14001f42f  mov     [rsp+130h+var_100], 2237h
0x14001f437  mov     r8d, 0Dh
0x14001f43d  mov     [rsp+130h+var_108], rax
0x14001f442  mov     dl, 5
0x14001f444  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001f44b  mov     [rsp+130h+var_110], rax
0x14001f450  call    WPP_RECORDER_SF_sDd
0x14001f455  mov     rcx, rdi
0x14001f458  call    WcReleaseUnionContext
0x14001f45d  mov     eax, ebx
0x14001f45f  mov     rcx, [rbp+4Fh+var_50]
0x14001f463  xor     rcx, rsp; StackCookie
0x14001f466  call    __security_check_cookie
0x14001f46b  add     rsp, 0F8h
0x14001f472  pop     r15
0x14001f474  pop     r14
0x14001f476  pop     r13
0x14001f478  pop     r12
0x14001f47a  pop     rdi
0x14001f47b  pop     rsi
0x14001f47c  pop     rbx
0x14001f47d  pop     rbp
0x14001f47e  retn
```
