# TLoad64BitDllsMgr::IsValidCapability(void *,ushort,ulong *)

- ea: `0x1400073ac`
- end: `0x140007540`
- name: `?IsValidCapability@TLoad64BitDllsMgr@@IEBAHPEAXGPEAK@Z`
- size: `404`
- prototype: `int(TLoad64BitDllsMgr *__hidden this, void *, unsigned __int16, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400069b8`

## callees

- `0x140001ee0`
- `0x140005f18`
- `0x1400073ac`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x14000747a`
- `WINSPOOL!GetPrinterDataW` at `0x1400074ee`
- `WINSPOOL!GetPrinterDataW` at `0x14000747a`
- `WINSPOOL!GetPrinterDataW` at `0x1400074ee`

## pseudocode

```c
__int64 __fastcall TLoad64BitDllsMgr::IsValidCapability(
        TLoad64BitDllsMgr *this,
        void *a2,
        unsigned __int16 a3,
        unsigned int *a4)
{
  unsigned int v6; // ebx
  int v7; // esi
  unsigned int v8; // eax
  __int64 nSize; // [rsp+20h] [rbp-E0h]
  DWORD pType; // [rsp+30h] [rbp-D0h] BYREF
  BYTE pData[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD pcbNeeded; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v14[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  WCHAR pValueName[264]; // [rsp+40h] [rbp-C0h] BYREF

  pType = 0;
  *(_DWORD *)v14 = 0;
  v6 = 0;
  pcbNeeded = 0;
  *(_DWORD *)pData = 0;
  if ( a3 && a4 )
  {
    v7 = a3;
    if ( a3 <= 0x23u )
    {
      v6 = 1;
      *a4 = *((_DWORD *)&DeviceCapsReqSize + a3 - 1);
      return v6;
    }
    if ( (int)StringCchPrintfW(pValueName, 0x104u, L"%s%x", &cszCustomCapabilityType, a3) >= 0
      && !GetPrinterDataW(a2, pValueName, &pType, pData, 4u, &pcbNeeded)
      && pType == 4 )
    {
      switch ( *(_DWORD *)pData )
      {
        case 0:
          v8 = 0;
          goto LABEL_17;
        case 1:
          v6 = 1;
          v8 = 1;
LABEL_18:
          *a4 = v8;
          return v6;
        case 2:
          LODWORD(nSize) = v7;
          if ( (int)StringCchPrintfW(pValueName, 0x104u, L"%s%x", &cszCustomCapabilitySize, nSize) >= 0
            && !GetPrinterDataW(a2, pValueName, &pType, v14, 4u, &pcbNeeded)
            && pType == 4 )
          {
            v8 = *(_DWORD *)v14;
LABEL_17:
            v6 = 1;
            goto LABEL_18;
          }
          break;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1400073ac  mov     [rsp-8+arg_0], rbx
0x1400073b1  push    rbp
0x1400073b2  push    rsi
0x1400073b3  push    rdi
0x1400073b4  push    r14
0x1400073b6  push    r15
0x1400073b8  lea     rbp, [rsp-160h]
0x1400073c0  sub     rsp, 260h
0x1400073c7  mov     rax, cs:__security_cookie
0x1400073ce  xor     rax, rsp
0x1400073d1  mov     [rbp+180h+var_30], rax
0x1400073d8  xor     r15d, r15d
0x1400073db  mov     rdi, r9
0x1400073de  mov     [rsp+280h+pType], r15d
0x1400073e3  mov     r14, rdx
0x1400073e6  mov     dword ptr [rsp+280h+var_244], r15d
0x1400073eb  mov     ebx, r15d
0x1400073ee  mov     [rsp+280h+var_248], r15d
0x1400073f3  mov     dword ptr [rsp+280h+pData], r15d
0x1400073f8  test    r8w, r8w
0x1400073fc  jz      loc_140007518
0x140007402  test    r9, r9
0x140007405  jz      loc_140007518
0x14000740b  movzx   esi, r8w
0x14000740f  cmp     r8w, 23h ; '#'
0x140007414  ja      short loc_14000742D
0x140007416  lea     rcx, ?DeviceCapsReqSize@@3PAKA; ulong near * DeviceCapsReqSize
0x14000741d  mov     eax, [rcx+rsi*4-4]
0x140007421  lea     ebx, [r15+1]
0x140007425  mov     [r9], eax
0x140007428  jmp     loc_140007518
0x14000742d  lea     r9, ?cszCustomCapabilityType@@3PAGA; "CustomDeviceCapabilityType_"
0x140007434  mov     dword ptr [rsp+280h+nSize], esi
0x140007438  lea     r8, aSX; "%s%x"
0x14000743f  mov     edx, 104h; unsigned __int64
0x140007444  lea     rcx, [rsp+280h+pValueName]; unsigned __int16 *
0x140007449  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000744e  test    eax, eax
0x140007450  js      loc_140007518
0x140007456  lea     rax, [rsp+280h+var_248]
0x14000745b  mov     rcx, r14; hPrinter
0x14000745e  mov     [rsp+280h+pcbNeeded], rax; pcbNeeded
0x140007463  lea     r9, [rsp+280h+pData]; pData
0x140007468  lea     r8, [rsp+280h+pType]; pType
0x14000746d  mov     dword ptr [rsp+280h+nSize], 4; nSize
0x140007475  lea     rdx, [rsp+280h+pValueName]; pValueName
0x14000747a  call    cs:__imp_GetPrinterDataW
0x140007480  test    eax, eax
0x140007482  jnz     loc_140007518
0x140007488  cmp     [rsp+280h+pType], 4
0x14000748d  jnz     loc_140007518
0x140007493  mov     ecx, dword ptr [rsp+280h+pData]
0x140007497  test    ecx, ecx
0x140007499  jz      short loc_14000750E
0x14000749b  sub     ecx, 1
0x14000749e  jz      short loc_140007505
0x1400074a0  cmp     ecx, 1
0x1400074a3  jnz     short loc_140007518
0x1400074a5  lea     r9, ?cszCustomCapabilitySize@@3PAGA; "CustomDeviceCapabilitySize_"
0x1400074ac  mov     dword ptr [rsp+280h+nSize], esi
0x1400074b0  lea     r8, aSX; "%s%x"
0x1400074b7  mov     edx, 104h; unsigned __int64
0x1400074bc  lea     rcx, [rsp+280h+pValueName]; unsigned __int16 *
0x1400074c1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400074c6  test    eax, eax
0x1400074c8  js      short loc_140007518
0x1400074ca  lea     rax, [rsp+280h+var_248]
0x1400074cf  mov     rcx, r14; hPrinter
0x1400074d2  mov     [rsp+280h+pcbNeeded], rax; pcbNeeded
0x1400074d7  lea     r9, [rsp+280h+var_244]; pData
0x1400074dc  lea     r8, [rsp+280h+pType]; pType
0x1400074e1  mov     dword ptr [rsp+280h+nSize], 4; nSize
0x1400074e9  lea     rdx, [rsp+280h+pValueName]; pValueName
0x1400074ee  call    cs:__imp_GetPrinterDataW
0x1400074f4  test    eax, eax
0x1400074f6  jnz     short loc_140007518
0x1400074f8  cmp     [rsp+280h+pType], 4
0x1400074fd  jnz     short loc_140007518
0x1400074ff  mov     eax, dword ptr [rsp+280h+var_244]
0x140007503  jmp     short loc_140007511
0x140007505  mov     ebx, 1
0x14000750a  mov     eax, ebx
0x14000750c  jmp     short loc_140007516
0x14000750e  mov     eax, r15d
0x140007511  mov     ebx, 1
0x140007516  mov     [rdi], eax
0x140007518  mov     eax, ebx
0x14000751a  mov     rcx, [rbp+180h+var_30]
0x140007521  xor     rcx, rsp; StackCookie
0x140007524  call    __security_check_cookie
0x140007529  mov     rbx, [rsp+280h+arg_0]
0x140007531  add     rsp, 260h
0x140007538  pop     r15
0x14000753a  pop     r14
0x14000753c  pop     rdi
0x14000753d  pop     rsi
0x14000753e  pop     rbp
0x14000753f  retn
```
