# SetRegistryValue

- ea: `0x1800420f0`
- end: `0x1800424d6`
- name: `SetRegistryValue`
- size: `998`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18003bc7c`
- `0x1800463e4`

## callees

- `0x18002f08c`
- `0x1800404a4`
- `0x180041744`
- `0x1800419f0`
- `0x180042054`
- `0x1800420f0`
- `0x1800424dc`
- `0x1800425f0`
- `0x180042a80`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004213f`
- `msvcrt!_wcsicmp` at `0x180042151`
- `msvcrt!_wcsicmp` at `0x180042163`
- `msvcrt!_wcsicmp` at `0x18004213f`
- `msvcrt!_wcsicmp` at `0x180042151`
- `msvcrt!_wcsicmp` at `0x180042163`
- `msvcrt!free` at `0x180042463`
- `msvcrt!free` at `0x180042463`
- `msvcrt!_wtol` at `0x1800422fb`
- `msvcrt!_wtol` at `0x1800422fb`
- `ADVAPI32!RegSetValueExW` at `0x1800423e1`
- `ADVAPI32!RegSetValueExW` at `0x1800423e1`
- `ADVAPI32!RegCreateKeyExW` at `0x180042358`
- `ADVAPI32!RegCreateKeyExW` at `0x180042358`
- `ADVAPI32!RegCloseKey` at `0x180042454`
- `ADVAPI32!RegCloseKey` at `0x180042454`

## string_xrefs

- `0x180042197`: `SetRegistryValue(%S\%S %S %d)`
- `0x18004238b`: `RegCreateKeyEx (HKLM\%S) failed with 0x%x`
- `0x180042408`: `RegSetValueEx (HKLM\%S\%S) failed with 0x%x`

## pseudocode

```c
__int64 __fastcall SetRegistryValue(HKEY a1, const WCHAR *a2, const WCHAR *a3, wchar_t *a4, __int64 a5)
{
  unsigned int i; // ebx
  DWORD RegistryValueType; // r13d
  _WORD *v10; // r8
  DWORD v11; // esi
  const BYTE *v12; // rdi
  __int16 *v13; // rdi
  _WORD *v14; // rcx
  _BYTE *v15; // rdx
  __int16 v16; // bx
  __int64 v17; // rbx
  __int64 v18; // r8
  __int64 v19; // rax
  unsigned int v20; // ebx
  _WORD v22[2]; // [rsp+50h] [rbp-21h] BYREF
  int v23; // [rsp+54h] [rbp-1Dh] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-19h] BYREF
  void *Block[2]; // [rsp+60h] [rbp-11h] BYREF
  _WORD *v26; // [rsp+70h] [rbp-1h]

  phkResult = 0;
  for ( i = 0; i < 0x17; ++i )
  {
    if ( !_wcsicmp(a2, IASKEYS[3 * (int)i])
      && !_wcsicmp(a3, IASKEYS[3 * (int)i + 1])
      && !_wcsicmp(a4, IASKEYS[3 * (int)i + 2]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WppDbgPrint("SetRegistryValue(%S\\%S %S %d)");
        WPP_SF_sSSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3, (__int64)a4, *(_WORD *)a5);
      }
      v26 = 0;
      RegistryValueType = GetRegistryValueType(a4);
      v10 = 0;
      *(_OWORD *)Block = 0;
      if ( RegistryValueType == 1 )
      {
        v12 = *(const BYTE **)(a5 + 8);
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)&v12[2 * v19] );
        v11 = 2 * v19 + 2;
      }
      else if ( RegistryValueType == 4 )
      {
        v23 = _wtol(*(const wchar_t **)(a5 + 8));
        v12 = (const BYTE *)&v23;
        v11 = 4;
      }
      else
      {
        v11 = 0;
        if ( RegistryValueType == 7 )
        {
          v13 = *(__int16 **)(a5 + 8);
          if ( v13 )
          {
            v14 = Block[1];
            v15 = Block[0];
            do
            {
              if ( !*v13 )
                break;
              if ( *v13 != 34 )
              {
                v16 = 0;
                if ( *v13 != 44 )
                  v16 = *v13;
                v22[0] = v16;
                if ( v22 >= v14 || v15 > (_BYTE *)v22 )
                {
                  if ( v14 == v10 )
                  {
                    std::vector<unsigned short>::_Reserve(Block, v15);
                    v10 = v26;
                    v14 = Block[1];
                    v15 = Block[0];
                  }
                  *v14 = v16;
                }
                else
                {
                  v17 = ((char *)v22 - v15) >> 1;
                  if ( v14 == v10 )
                  {
                    std::vector<unsigned short>::_Reserve(Block, v15);
                    v10 = v26;
                    v14 = Block[1];
                    v15 = Block[0];
                  }
                  *v14 = *(_WORD *)&v15[2 * v17];
                }
                Block[1] = ++v14;
                ++v11;
              }
              ++v13;
            }
            while ( v13 );
          }
          LOWORD(v23) = 0;
          std::vector<unsigned short>::push_back(Block, &v23, v10);
          LOWORD(v23) = 0;
          std::vector<unsigned short>::push_back(Block, &v23, v18);
          v12 = (const BYTE *)Block[0];
          v11 = 2 * v11 + 4;
        }
        else
        {
          v12 = 0;
        }
      }
      v20 = RegCreateKeyExW(a1, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
      if ( v20 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WppDbgPrint("RegCreateKeyEx (HKLM\\%S) failed with 0x%x");
          WPP_SF_sSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            (unsigned int)&WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
            (unsigned int)"NAPBASE",
            (__int64)a2,
            v20);
        }
      }
      else
      {
        v20 = RegSetValueExW(phkResult, a3, 0, RegistryValueType, v12, v11);
        if ( v20
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WppDbgPrint("RegSetValueEx (HKLM\\%S\\%S) failed with 0x%x");
          WPP_SF_sSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3, v20);
        }
      }
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( Block[0] )
        free(Block[0]);
      return v20;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WppDbgPrint("Silently discarding invalid Reg input %S\\%S with type %S");
    WPP_SF_sSSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3, (__int64)a4);
  }
  return 0;
}

```

## disassembly

```asm
0x1800420f0  mov     [rsp-8+hKey], rcx
0x1800420f5  push    rbp
0x1800420f6  push    rbx
0x1800420f7  push    rsi
0x1800420f8  push    rdi
0x1800420f9  push    r12
0x1800420fb  push    r13
0x1800420fd  push    r14
0x1800420ff  push    r15
0x180042101  lea     rbp, [rsp-17h]
0x180042106  sub     rsp, 88h
0x18004210d  xor     r14d, r14d
0x180042110  lea     r13, IASKEYS
0x180042117  mov     [rbp+4Fh+var_68], r14
0x18004211b  mov     ebx, r14d
0x18004211e  mov     rdi, r9
0x180042121  mov     r12, r8
0x180042124  mov     r15, rdx
0x180042127  cmp     ebx, 17h
0x18004212a  jnb     loc_18004246D
0x180042130  movsxd  rax, ebx
0x180042133  mov     rcx, r15; String1
0x180042136  lea     rsi, [rax+rax*2]
0x18004213a  mov     rdx, [r13+rsi*8+0]; String2
0x18004213f  call    cs:__imp__wcsicmp
0x180042145  test    eax, eax
0x180042147  jnz     short loc_18004216D
0x180042149  mov     rdx, [r13+rsi*8+8]; String2
0x18004214e  mov     rcx, r12; String1
0x180042151  call    cs:__imp__wcsicmp
0x180042157  test    eax, eax
0x180042159  jnz     short loc_18004216D
0x18004215b  mov     rdx, [r13+rsi*8+10h]; String2
0x180042160  mov     rcx, rdi; String1
0x180042163  call    cs:__imp__wcsicmp
0x180042169  test    eax, eax
0x18004216b  jz      short loc_180042171
0x18004216d  inc     ebx
0x18004216f  jmp     short loc_180042127
0x180042171  mov     rax, cs:WPP_GLOBAL_Control
0x180042178  lea     r14, WPP_GLOBAL_Control
0x18004217f  mov     rbx, [rbp+4Fh+arg_20]
0x180042183  cmp     rax, r14
0x180042186  jz      short loc_1800421D6
0x180042188  cmp     byte ptr [rax+19h], 2
0x18004218c  jb      short loc_1800421D6
0x18004218e  test    byte ptr [rax+1Ch], 1
0x180042192  jz      short loc_1800421D6
0x180042194  movzx   eax, word ptr [rbx]
0x180042197  lea     rcx, aSetregistryval_0; "SetRegistryValue(%S\\%S %S %d)"
0x18004219e  mov     r9, rdi
0x1800421a1  mov     [rsp+0C0h+dwOptions], eax
0x1800421a5  mov     r8, r12
0x1800421a8  mov     rdx, r15
0x1800421ab  call    WppDbgPrint
0x1800421b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800421b7  movzx   eax, word ptr [rbx]
0x1800421ba  mov     dword ptr [rsp+0C0h+phkResult], eax; char
0x1800421be  mov     [rsp+0C0h+lpSecurityAttributes], rdi; __int64
0x1800421c3  mov     rcx, [rcx+10h]; LoggerHandle
0x1800421c7  mov     qword ptr [rsp+0C0h+samDesired], r12; __int64
0x1800421cc  mov     qword ptr [rsp+0C0h+dwOptions], r15; __int64
0x1800421d1  call    WPP_SF_sSSSd
0x1800421d6  mov     rcx, rdi; String1
0x1800421d9  call    GetRegistryValueType
0x1800421de  xor     r9d, r9d
0x1800421e1  mov     ecx, eax
0x1800421e3  mov     [rbp+4Fh+var_50], r9
0x1800421e7  xorps   xmm0, xmm0
0x1800421ea  mov     r13d, eax
0x1800421ed  mov     r8d, r9d
0x1800421f0  movdqu  xmmword ptr [rbp+4Fh+Block], xmm0
0x1800421f5  sub     ecx, 1
0x1800421f8  jz      loc_180042312
0x1800421fe  sub     ecx, 3
0x180042201  jz      loc_1800422F7
0x180042207  mov     esi, r9d
0x18004220a  cmp     ecx, 3
0x18004220d  jz      short loc_180042217
0x18004220f  mov     edi, r9d
0x180042212  jmp     loc_18004232B
0x180042217  mov     rdi, [rbx+8]
0x18004221b  test    rdi, rdi
0x18004221e  jz      loc_1800422C5
0x180042224  mov     rcx, [rbp+4Fh+Block+8]
0x180042228  mov     rdx, [rbp+4Fh+Block]
0x18004222c  cmp     r9w, [rdi]
0x180042230  jz      loc_1800422C5
0x180042236  mov     eax, 22h ; '"'
0x18004223b  cmp     ax, [rdi]
0x18004223e  jz      short loc_1800422BB
0x180042240  cmp     word ptr [rdi], 2Ch ; ','
0x180042244  lea     rax, [rbp+4Fh+var_70]
0x180042248  mov     ebx, r9d
0x18004224b  cmovnz  bx, [rdi]
0x18004224f  mov     [rbp+4Fh+var_70], bx
0x180042253  cmp     rax, rcx
0x180042256  jnb     short loc_180042291
0x180042258  lea     rax, [rbp+4Fh+var_70]
0x18004225c  cmp     rdx, rax
0x18004225f  ja      short loc_180042291
0x180042261  lea     rbx, [rbp+4Fh+var_70]
0x180042265  sub     rbx, rdx
0x180042268  sar     rbx, 1
0x18004226b  cmp     rcx, r8
0x18004226e  jnz     short loc_180042288
0x180042270  lea     rcx, [rbp+4Fh+Block]
0x180042274  call    ?_Reserve@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reserve(unsigned __int64)
0x180042279  mov     r8, [rbp+4Fh+var_50]
0x18004227d  xor     r9d, r9d
0x180042280  mov     rcx, [rbp+4Fh+Block+8]
0x180042284  mov     rdx, [rbp+4Fh+Block]
0x180042288  movzx   eax, word ptr [rdx+rbx*2]
0x18004228c  mov     [rcx], ax
0x18004228f  jmp     short loc_1800422B1
0x180042291  cmp     rcx, r8
0x180042294  jnz     short loc_1800422AE
0x180042296  lea     rcx, [rbp+4Fh+Block]
0x18004229a  call    ?_Reserve@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reserve(unsigned __int64)
0x18004229f  mov     r8, [rbp+4Fh+var_50]
0x1800422a3  xor     r9d, r9d
0x1800422a6  mov     rcx, [rbp+4Fh+Block+8]
0x1800422aa  mov     rdx, [rbp+4Fh+Block]
0x1800422ae  mov     [rcx], bx
0x1800422b1  add     rcx, 2
0x1800422b5  mov     [rbp+4Fh+Block+8], rcx
0x1800422b9  inc     esi
0x1800422bb  add     rdi, 2
0x1800422bf  jnz     loc_18004222C
0x1800422c5  lea     rdx, [rbp+4Fh+var_6C]
0x1800422c9  mov     word ptr [rbp+4Fh+var_6C], r9w
0x1800422ce  lea     rcx, [rbp+4Fh+Block]
0x1800422d2  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x1800422d7  xor     eax, eax
0x1800422d9  lea     rdx, [rbp+4Fh+var_6C]
0x1800422dd  lea     rcx, [rbp+4Fh+Block]
0x1800422e1  mov     word ptr [rbp+4Fh+var_6C], ax
0x1800422e5  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x1800422ea  mov     rdi, [rbp+4Fh+Block]
0x1800422ee  lea     esi, ds:4[rsi*2]
0x1800422f5  jmp     short loc_18004230D
0x1800422f7  mov     rcx, [rbx+8]; String
0x1800422fb  call    cs:__imp__wtol
0x180042301  mov     [rbp+4Fh+var_6C], eax
0x180042304  lea     rdi, [rbp+4Fh+var_6C]
0x180042308  mov     esi, 4
0x18004230d  xor     r9d, r9d
0x180042310  jmp     short loc_18004232B
0x180042312  mov     rdi, [rbx+8]
0x180042316  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004231a  inc     rax
0x18004231d  cmp     [rdi+rax*2], r9w
0x180042322  jnz     short loc_18004231A
0x180042324  lea     esi, ds:2[rax*2]
0x18004232b  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004232f  lea     rax, [rbp+4Fh+var_68]
0x180042333  mov     [rsp+0C0h+lpdwDisposition], r9; lpdwDisposition
0x180042338  xor     r8d, r8d; Reserved
0x18004233b  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180042340  mov     rdx, r15; lpSubKey
0x180042343  mov     [rsp+0C0h+lpSecurityAttributes], r9; lpSecurityAttributes
0x180042348  mov     [rsp+0C0h+samDesired], 2001Fh; samDesired
0x180042350  mov     [rsp+0C0h+dwOptions], r9d; dwOptions
0x180042355  xor     r9d, r9d; lpClass
0x180042358  call    cs:__imp_RegCreateKeyExW
0x18004235e  mov     ebx, eax
0x180042360  test    eax, eax
0x180042362  jz      short loc_1800423CB
0x180042364  mov     rax, cs:WPP_GLOBAL_Control
0x18004236b  cmp     rax, r14
0x18004236e  jz      loc_18004244B
0x180042374  cmp     byte ptr [rax+19h], 2
0x180042378  jb      loc_18004244B
0x18004237e  test    byte ptr [rax+1Ch], 1
0x180042382  jz      loc_18004244B
0x180042388  mov     r8d, ebx
0x18004238b  lea     rcx, aRegcreatekeyex; "RegCreateKeyEx (HKLM\\%S) failed with 0"...
0x180042392  mov     rdx, r15
0x180042395  call    WppDbgPrint
0x18004239a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800423a1  lea     r9, aNapbase; "NAPBASE"
0x1800423a8  mov     edx, 2Ah ; '*'
0x1800423ad  mov     [rsp+0C0h+samDesired], ebx
0x1800423b1  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x1800423b8  mov     qword ptr [rsp+0C0h+dwOptions], r15
0x1800423bd  mov     rcx, [rcx+10h]
0x1800423c1  call    WPP_SF_sSd
0x1800423c6  jmp     loc_18004244B
0x1800423cb  mov     rcx, [rbp+4Fh+var_68]; hKey
0x1800423cf  mov     r9d, r13d; dwType
0x1800423d2  mov     [rsp+0C0h+samDesired], esi; cbData
0x1800423d6  xor     r8d, r8d; Reserved
0x1800423d9  mov     rdx, r12; lpValueName
0x1800423dc  mov     qword ptr [rsp+0C0h+dwOptions], rdi; lpData
0x1800423e1  call    cs:__imp_RegSetValueExW
0x1800423e7  mov     ebx, eax
0x1800423e9  test    eax, eax
0x1800423eb  jz      short loc_18004244B
0x1800423ed  mov     rax, cs:WPP_GLOBAL_Control
0x1800423f4  cmp     rax, r14
0x1800423f7  jz      short loc_18004244B
0x1800423f9  cmp     byte ptr [rax+19h], 2
0x1800423fd  jb      short loc_18004244B
0x1800423ff  test    byte ptr [rax+1Ch], 1
0x180042403  jz      short loc_18004244B
0x180042405  mov     r9d, ebx
0x180042408  lea     rcx, aRegsetvalueexH; "RegSetValueEx (HKLM\\%S\\%S) failed wit"...
0x18004240f  mov     r8, r12
0x180042412  mov     rdx, r15
0x180042415  call    WppDbgPrint
0x18004241a  mov     rcx, cs:WPP_GLOBAL_Control
0x180042421  lea     r9, aNapbase; "NAPBASE"
0x180042428  mov     dword ptr [rsp+0C0h+lpSecurityAttributes], ebx; char
0x18004242c  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x180042433  mov     edx, 2Bh ; '+'
0x180042438  mov     qword ptr [rsp+0C0h+samDesired], r12; __int64
0x18004243d  mov     qword ptr [rsp+0C0h+dwOptions], r15; __int64
0x180042442  mov     rcx, [rcx+10h]; LoggerHandle
0x180042446  call    WPP_SF_sSSD
0x18004244b  mov     rcx, [rbp+4Fh+var_68]; hKey
0x18004244f  test    rcx, rcx
0x180042452  jz      short loc_18004245A
0x180042454  call    cs:__imp_RegCloseKey
0x18004245a  mov     rcx, [rbp+4Fh+Block]; Block
0x18004245e  test    rcx, rcx
0x180042461  jz      short loc_180042469
0x180042463  call    cs:__imp_free
0x180042469  mov     eax, ebx
0x18004246b  jmp     short loc_1800424C2
0x18004246d  mov     rax, cs:WPP_GLOBAL_Control
0x180042474  lea     r14, WPP_GLOBAL_Control
0x18004247b  cmp     rax, r14
0x18004247e  jz      short loc_1800424C0
0x180042480  cmp     byte ptr [rax+19h], 2
0x180042484  jb      short loc_1800424C0
0x180042486  test    byte ptr [rax+1Ch], 1
0x18004248a  jz      short loc_1800424C0
0x18004248c  mov     r9, rdi
0x18004248f  lea     rcx, aSilentlyDiscar; "Silently discarding invalid Reg input %"...
0x180042496  mov     r8, r12
0x180042499  mov     rdx, r15
0x18004249c  call    WppDbgPrint
0x1800424a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800424a8  mov     [rsp+0C0h+lpSecurityAttributes], rdi; __int64
0x1800424ad  mov     qword ptr [rsp+0C0h+samDesired], r12; __int64
0x1800424b2  mov     qword ptr [rsp+0C0h+dwOptions], r15; __int64
0x1800424b7  mov     rcx, [rcx+10h]; LoggerHandle
0x1800424bb  call    WPP_SF_sSSS
0x1800424c0  xor     eax, eax
0x1800424c2  add     rsp, 88h
0x1800424c9  pop     r15
0x1800424cb  pop     r14
0x1800424cd  pop     r13
0x1800424cf  pop     r12
0x1800424d1  pop     rdi
0x1800424d2  pop     rsi
0x1800424d3  pop     rbx
0x1800424d4  pop     rbp
0x1800424d5  retn
```
