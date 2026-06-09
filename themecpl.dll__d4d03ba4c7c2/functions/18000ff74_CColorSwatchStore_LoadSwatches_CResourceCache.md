# CColorSwatchStore::LoadSwatches(CResourceCache *)

- ea: `0x18000ff74`
- end: `0x18001010d`
- name: `?LoadSwatches@CColorSwatchStore@@QEAAJPEAVCResourceCache@@@Z`
- size: `409`
- prototype: `__int64 __fastcall(CColorSwatchStore *__hidden this, struct CResourceCache *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023aa4`
- `0x1800380d0`

## callees

- `0x18000f724`
- `0x18000f774`
- `0x18000f9c8`
- `0x18000fb80`
- `0x18000fc50`
- `0x18000ff74`

## import_xrefs

- `SHLWAPI!SHRegCloseUSKey` at `0x1800100f3`
- `SHLWAPI!SHRegCloseUSKey` at `0x1800100f3`
- `SHLWAPI!SHRegQueryInfoUSKeyW` at `0x18001002d`
- `SHLWAPI!SHRegQueryInfoUSKeyW` at `0x18001002d`
- `SHLWAPI!SHRegOpenUSKeyW` at `0x18000ffff`
- `SHLWAPI!SHRegOpenUSKeyW` at `0x18000ffff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ffa0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ffa0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ff88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ff88`

## pseudocode

```c
__int64 __fastcall CColorSwatchStore::LoadSwatches(CColorSwatchStore *this, struct CResourceCache *a2)
{
  HANDLE ProcessHeap; // rax
  char *v5; // rax
  int SwatchConfig; // ebx
  CColorSwatchStore *v7; // rcx
  DWORD v8; // edi
  __int64 v9; // rcx
  __int64 v10; // r8
  int fIgnoreHKCU; // [rsp+20h] [rbp-40h]
  __int128 v13; // [rsp+30h] [rbp-30h] BYREF
  __int64 v14; // [rsp+40h] [rbp-20h]
  __int16 v15; // [rsp+48h] [rbp-18h]
  int v16; // [rsp+4Ch] [rbp-14h]
  char v17; // [rsp+50h] [rbp-10h]
  DWORD pcSubKeys; // [rsp+90h] [rbp+30h] BYREF
  HUSKEY phNewUSKey; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+48h] BYREF

  ProcessHeap = GetProcessHeap();
  v5 = (char *)HeapAlloc(ProcessHeap, 8u, 0x30u);
  if ( v5 )
  {
    *(_DWORD *)v5 = *(_DWORD *)v5 & 0x80000000 | 0x20000000;
    *(_OWORD *)(v5 + 8) = 0;
    SwatchConfig = 0;
    *(_OWORD *)(v5 + 24) = 0;
    *((_QWORD *)v5 + 5) = 0;
    *(_QWORD *)this = v5;
    phNewUSKey = 0;
    if ( !SHRegOpenUSKeyW(
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Control Panel\\Glass Colorization\\Swatches",
            0x20019u,
            0,
            &phNewUSKey,
            0) )
    {
      pcSubKeys = 0;
      if ( !SHRegQueryInfoUSKeyW(phNewUSKey, &pcSubKeys, 0, 0, 0, SHREGENUM_DEFAULT) )
      {
        v8 = 0;
        while ( v8 < pcSubKeys )
        {
          v15 = 0;
          v16 = 0;
          v17 = 0;
          v14 = 0;
          v13 = 0;
          SwatchConfig = CColorSwatchStore::LoadSwatchConfig(v7, a2, phNewUSKey, v8, (struct CColorSwatchConfig *)&v13);
          if ( SwatchConfig >= 0 )
          {
            v9 = *(_QWORD *)this;
            v20 = 0;
            SwatchConfig = DirectUI::DynamicArrayBase<CColorSwatchConfig,DirectUI::DoubleAllocationPolicy<CColorSwatchConfig>,1,0>::AddPtr(
                             v9,
                             &v20);
            if ( SwatchConfig >= 0 )
            {
              if ( *((_QWORD *)&v13 + 1) )
                v10 = (unsigned int)**((_DWORD **)&v13 + 1);
              else
                v10 = 0;
              LOWORD(fIgnoreHKCU) = v15;
              SwatchConfig = CColorSwatchConfig::Initialize(v20, v13, v10, v14, fIgnoreHKCU, v16);
            }
          }
          CColorSwatchConfig::FreeStrings((CColorSwatchConfig *)&v13);
          ++v8;
          if ( SwatchConfig < 0 )
          {
            CColorSwatchStore::FlushSwatchData(this);
            break;
          }
        }
      }
      SHRegCloseUSKey(phNewUSKey);
    }
  }
  else
  {
    *(_QWORD *)this = 0;
    return (unsigned int)-2147024882;
  }
  return (unsigned int)SwatchConfig;
}

```

## disassembly

```asm
0x18000ff74  push    rbp
0x18000ff76  push    rbx
0x18000ff77  push    rsi
0x18000ff78  push    rdi
0x18000ff79  push    r14
0x18000ff7b  mov     rbp, rsp
0x18000ff7e  sub     rsp, 60h
0x18000ff82  mov     r14, rdx
0x18000ff85  mov     rsi, rcx
0x18000ff88  call    cs:__imp_GetProcessHeap
0x18000ff8f  nop     dword ptr [rax+rax+00h]
0x18000ff94  mov     edx, 8; dwFlags
0x18000ff99  mov     rcx, rax; hHeap
0x18000ff9c  lea     r8d, [rdx+28h]; dwBytes
0x18000ffa0  call    cs:__imp_HeapAlloc
0x18000ffa7  nop     dword ptr [rax+rax+00h]
0x18000ffac  mov     rcx, rax
0x18000ffaf  test    rax, rax
0x18000ffb2  jnz     short loc_18000FFC1
0x18000ffb4  mov     [rsi], rax
0x18000ffb7  mov     ebx, 8007000Eh
0x18000ffbc  jmp     loc_1800100FF
0x18000ffc1  mov     eax, [rax]
0x18000ffc3  lea     r9, [rbp+phNewUSKey]; phNewUSKey
0x18000ffc7  and     eax, 0A0000000h
0x18000ffcc  xorps   xmm0, xmm0
0x18000ffcf  bts     eax, 1Dh
0x18000ffd3  xor     r8d, r8d; hRelativeUSKey
0x18000ffd6  mov     [rcx], eax
0x18000ffd8  mov     edx, 20019h; samDesired
0x18000ffdd  movups  xmmword ptr [rcx+8], xmm0
0x18000ffe1  xor     eax, eax
0x18000ffe3  xor     ebx, ebx
0x18000ffe5  movups  xmmword ptr [rcx+18h], xmm0
0x18000ffe9  mov     [rcx+28h], rax
0x18000ffed  mov     [rsi], rcx
0x18000fff0  lea     rcx, pwzPath; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000fff7  mov     [rbp+phNewUSKey], rax
0x18000fffb  mov     [rsp+60h+fIgnoreHKCU], eax; fIgnoreHKCU
0x18000ffff  call    cs:__imp_SHRegOpenUSKeyW
0x180010006  nop     dword ptr [rax+rax+00h]
0x18001000b  test    eax, eax
0x18001000d  jnz     loc_1800100FF
0x180010013  mov     rcx, [rbp+phNewUSKey]; hUSKey
0x180010017  lea     rdx, [rbp+pcSubKeys]; pcSubKeys
0x18001001b  mov     [rsp+60h+enumRegFlags], ebx; enumRegFlags
0x18001001f  xor     r9d, r9d; pcValues
0x180010022  xor     r8d, r8d; pcchMaxSubKeyLen
0x180010025  mov     qword ptr [rsp+60h+fIgnoreHKCU], rbx; pcchMaxValueNameLen
0x18001002a  mov     [rbp+pcSubKeys], ebx
0x18001002d  call    cs:__imp_SHRegQueryInfoUSKeyW
0x180010034  nop     dword ptr [rax+rax+00h]
0x180010039  test    eax, eax
0x18001003b  jnz     loc_1800100EF
0x180010041  xor     edi, edi
0x180010043  cmp     edi, [rbp+pcSubKeys]
0x180010046  jnb     loc_1800100EF
0x18001004c  mov     r8, [rbp+phNewUSKey]; void *
0x180010050  xor     eax, eax
0x180010052  mov     [rbp+var_18], ax
0x180010056  xorps   xmm0, xmm0
0x180010059  mov     [rbp+var_14], eax
0x18001005c  mov     r9d, edi; unsigned int
0x18001005f  mov     [rbp+var_10], al
0x180010062  mov     rdx, r14; struct CResourceCache *
0x180010065  lea     rax, [rbp+var_30]
0x180010069  mov     [rbp+var_20], 0
0x180010071  mov     qword ptr [rsp+60h+fIgnoreHKCU], rax; struct CColorSwatchConfig *
0x180010076  movdqu  [rbp+var_30], xmm0
0x18001007b  call    ?LoadSwatchConfig@CColorSwatchStore@@AEAAJPEAVCResourceCache@@PEAXIPEAVCColorSwatchConfig@@@Z; CColorSwatchStore::LoadSwatchConfig(CResourceCache *,void *,uint,CColorSwatchConfig *)
0x180010080  mov     ebx, eax
0x180010082  test    eax, eax
0x180010084  js      short loc_1800100D4
0x180010086  mov     rcx, [rsi]
0x180010089  lea     rdx, [rbp+arg_18]
0x18001008d  mov     [rbp+arg_18], 0
0x180010095  call    ?AddPtr@?$DynamicArrayBase@VCColorSwatchConfig@@V?$DoubleAllocationPolicy@VCColorSwatchConfig@@@DirectUI@@$00$0A@@DirectUI@@QEAAJPEAPEAVCColorSwatchConfig@@@Z; DirectUI::DynamicArrayBase<CColorSwatchConfig,DirectUI::DoubleAllocationPolicy<CColorSwatchConfig>,1,0>::AddPtr(CColorSwatchConfig * *)
0x18001009a  mov     ebx, eax
0x18001009c  test    eax, eax
0x18001009e  js      short loc_1800100D4
0x1800100a0  mov     rax, qword ptr [rbp+var_30+8]
0x1800100a4  mov     ecx, [rbp+var_14]
0x1800100a7  movzx   edx, [rbp+var_18]
0x1800100ab  test    rax, rax
0x1800100ae  jz      short loc_1800100B5
0x1800100b0  mov     r8d, [rax]
0x1800100b3  jmp     short loc_1800100B8
0x1800100b5  xor     r8d, r8d
0x1800100b8  mov     r9, [rbp+var_20]
0x1800100bc  mov     [rsp+60h+enumRegFlags], ecx
0x1800100c0  mov     rcx, [rbp+arg_18]
0x1800100c4  mov     word ptr [rsp+60h+fIgnoreHKCU], dx
0x1800100c9  mov     rdx, qword ptr [rbp+var_30]
0x1800100cd  call    ?Initialize@CColorSwatchConfig@@QEAAJPEAGVCColorizationColor@@0GI@Z; CColorSwatchConfig::Initialize(ushort *,CColorizationColor,ushort *,ushort,uint)
0x1800100d2  mov     ebx, eax
0x1800100d4  lea     rcx, [rbp+var_30]; this
0x1800100d8  call    ?FreeStrings@CColorSwatchConfig@@QEAAXXZ; CColorSwatchConfig::FreeStrings(void)
0x1800100dd  inc     edi
0x1800100df  test    ebx, ebx
0x1800100e1  jns     loc_180010043
0x1800100e7  mov     rcx, rsi; this
0x1800100ea  call    ?FlushSwatchData@CColorSwatchStore@@QEAAXXZ; CColorSwatchStore::FlushSwatchData(void)
0x1800100ef  mov     rcx, [rbp+phNewUSKey]; hUSKey
0x1800100f3  call    cs:__imp_SHRegCloseUSKey
0x1800100fa  nop     dword ptr [rax+rax+00h]
0x1800100ff  mov     eax, ebx
0x180010101  add     rsp, 60h
0x180010105  pop     r14
0x180010107  pop     rdi
0x180010108  pop     rsi
0x180010109  pop     rbx
0x18001010a  pop     rbp
0x18001010b  retn
```
