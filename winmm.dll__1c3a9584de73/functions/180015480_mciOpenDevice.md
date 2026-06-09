# mciOpenDevice

- ea: `0x180015480`
- end: `0x180015841`
- name: `mciOpenDevice`
- size: `961`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800102a8`

## callees

- `0x18000b6d4`
- `0x180013b4c`
- `0x180013e9c`
- `0x180013f64`
- `0x180014ca8`
- `0x180014e04`
- `0x180015180`
- `0x180015480`
- `0x18001a408`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015634`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800156d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800157d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800157ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015804`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015634`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800156d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800157d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800157ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015804`

## pseudocode

```c
int __fastcall mciOpenDevice(unsigned int a1, struct tagMCI_OPEN_PARMSW *a2, void **a3)
{
  int v3; // r12d
  void **v4; // rax
  void *v7; // rsi
  WCHAR *v8; // r14
  int result; // eax
  int v10; // r13d
  const WCHAR *lpstrElementName; // rcx
  MCIDEVICEID DeviceIDFromElementIDW; // eax
  WCHAR *v13; // rax
  const WCHAR *v14; // r15
  WCHAR *v15; // rax
  void **v16; // rbp
  const WCHAR *v17; // rax
  int v18; // eax
  int Device; // ebp
  int v20; // eax
  LPVOID v21; // [rsp+20h] [rbp-58h] BYREF
  LPCWSTR v22; // [rsp+28h] [rbp-50h] BYREF
  const WCHAR *lpstrDeviceType; // [rsp+30h] [rbp-48h]
  const WCHAR *lpstrAlias; // [rsp+38h] [rbp-40h]
  const WCHAR *lpKeyName; // [rsp+88h] [rbp+10h]
  LPVOID lpMem; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  v4 = a3;
  lpMem = 0;
  v7 = 0;
  v8 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids);
    }
    return 297;
  }
  v10 = 0;
  lpstrDeviceType = a2->lpstrDeviceType;
  lpstrElementName = a2->lpstrElementName;
  lpstrAlias = a2->lpstrAlias;
  lpKeyName = lpstrElementName;
  if ( (a1 & 0x1000) != 0 )
  {
    result = mciExtractTypeFromID(a2);
    if ( result )
      return result;
    lpstrElementName = lpKeyName;
    v10 = 1;
    v4 = a3;
  }
  if ( (a1 & 0x200) == 0 )
  {
    if ( (a1 & 0x2000) == 0 )
      return 273;
    lpstrElementName = a2->lpstrDeviceType;
  }
  if ( !lpstrElementName )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids);
    }
    return 263;
  }
  if ( (a1 & 0x800) != 0 )
  {
    DeviceIDFromElementIDW = mciGetDeviceIDFromElementIDW((DWORD)lpstrElementName, a2->lpstrDeviceType);
  }
  else
  {
    if ( (a1 & 0x400) != 0 )
      lpstrElementName = a2->lpstrAlias;
    DeviceIDFromElementIDW = mciGetDeviceIDInternal(lpstrElementName, v4[2]);
  }
  if ( DeviceIDFromElementIDW )
    return (a1 & 0x400) != 0 ? 289 : 265;
  if ( v10 )
  {
    v16 = a3;
    v14 = lpKeyName;
    goto LABEL_60;
  }
  if ( (a1 & 0x200) != 0 && (a1 & 0x2000) == 0 )
  {
    v13 = (WCHAR *)winmmAlloc(0xA0u);
    v7 = v13;
    if ( v13 )
    {
      v14 = lpKeyName;
      if ( !mciExtractDeviceType(lpKeyName, v13) )
      {
        HeapFree(hHeap, 0, v7);
        return 281;
      }
      a2->lpstrDeviceType = (LPCWSTR)v7;
      a1 |= 0x2000u;
      goto LABEL_39;
    }
    return 264;
  }
  if ( (a1 & 0x2200) != 0x2000 )
  {
LABEL_38:
    v14 = lpKeyName;
LABEL_39:
    v16 = a3;
    goto LABEL_40;
  }
  v15 = (WCHAR *)winmmAlloc(0xA0u);
  v7 = v15;
  if ( !v15 )
    return 264;
  if ( mciExtractDeviceType(a2->lpstrDeviceType, v15) )
  {
    a1 |= 0x200u;
    a2->lpstrElementName = a2->lpstrDeviceType;
    a2->lpstrDeviceType = (LPCWSTR)v7;
    goto LABEL_38;
  }
  v22 = a2->lpstrDeviceType;
  HeapFree(hHeap, 0, v7);
  v21 = 0;
  v18 = mciEatToken(&v22, 33, &v21, 1);
  v7 = v21;
  Device = v18;
  if ( !v18 )
  {
    if ( !v21 )
      goto LABEL_38;
    v20 = mciEatToken(&v22, 0, &lpMem, 1);
    v8 = (WCHAR *)lpMem;
    Device = v20;
    if ( !v20 )
    {
      v16 = a3;
      if ( lpMem && *(_WORD *)lpMem )
      {
        if ( (a1 & 0x400) == 0 && mciGetDeviceIDInternal((LPCWSTR)lpMem, a3[2]) )
        {
          Device = 265;
          goto LABEL_52;
        }
        a2->lpstrElementName = v8;
        a1 |= 0x200u;
        a2->lpstrDeviceType = (LPCWSTR)v7;
      }
      v14 = lpKeyName;
LABEL_40:
      if ( (a1 & 0x400) == 0 )
      {
        if ( (a1 & 0x200) == 0 )
        {
          v17 = a2->lpstrDeviceType;
LABEL_57:
          if ( v17 )
          {
            a2->lpstrAlias = v17;
            a1 |= 0x400u;
            v3 = 1;
          }
          goto LABEL_60;
        }
        if ( (a1 & 0x800) == 0 )
        {
          v17 = a2->lpstrElementName;
          goto LABEL_57;
        }
      }
LABEL_60:
      Device = mciLoadDevice(a1, a2, v16, v3);
LABEL_61:
      if ( v8 )
        HeapFree(hHeap, 0, v8);
      goto LABEL_63;
    }
LABEL_52:
    v14 = lpKeyName;
    goto LABEL_61;
  }
  v14 = lpKeyName;
LABEL_63:
  if ( v7 )
    HeapFree(hHeap, 0, v7);
  if ( v10 )
    HeapFree(hHeap, 0, (LPVOID)a2->lpstrDeviceType);
  a2->lpstrDeviceType = lpstrDeviceType;
  a2->lpstrAlias = lpstrAlias;
  result = Device;
  a2->lpstrElementName = v14;
  return result;
}

```

## disassembly

```asm
0x180015480  mov     r11, rsp
0x180015483  mov     [r11+8], rbx
0x180015487  mov     [r11+18h], r8
0x18001548b  push    rbp
0x18001548c  push    rsi
0x18001548d  push    rdi
0x18001548e  push    r12
0x180015490  push    r13
0x180015492  push    r14
0x180015494  push    r15
0x180015496  sub     rsp, 40h
0x18001549a  xor     r12d, r12d
0x18001549d  mov     rax, r8
0x1800154a0  mov     [r11+20h], r12
0x1800154a4  mov     rbx, rdx
0x1800154a7  mov     edi, ecx
0x1800154a9  mov     esi, r12d
0x1800154ac  mov     r14d, r12d
0x1800154af  test    rdx, rdx
0x1800154b2  jnz     short loc_1800154F3
0x1800154b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154bb  lea     rax, WPP_GLOBAL_Control
0x1800154c2  cmp     rcx, rax
0x1800154c5  jz      short loc_1800154E9
0x1800154c7  test    dword ptr [rcx+1Ch], 400000h
0x1800154ce  jz      short loc_1800154E9
0x1800154d0  cmp     byte ptr [rcx+19h], 2
0x1800154d4  jb      short loc_1800154E9
0x1800154d6  mov     rcx, [rcx+10h]
0x1800154da  lea     edx, [rbx+28h]
0x1800154dd  lea     r8, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids
0x1800154e4  call    WPP_SF_
0x1800154e9  mov     eax, 129h
0x1800154ee  jmp     loc_180015829
0x1800154f3  mov     rcx, [rdx+0Ch]
0x1800154f7  mov     r13d, r12d
0x1800154fa  mov     [rsp+78h+var_48], rcx
0x1800154ff  mov     rcx, [rdx+14h]
0x180015503  mov     rdx, [rdx+1Ch]
0x180015507  mov     [rsp+78h+var_40], rdx
0x18001550c  mov     [rsp+78h+lpKeyName], rcx
0x180015514  bt      edi, 0Ch
0x180015518  jnb     short loc_18001553E
0x18001551a  mov     rcx, rbx; struct tagMCI_OPEN_PARMSW *
0x18001551d  call    ?mciExtractTypeFromID@@YAIPEAUtagMCI_OPEN_PARMSW@@@Z; mciExtractTypeFromID(tagMCI_OPEN_PARMSW *)
0x180015522  test    eax, eax
0x180015524  jnz     loc_180015829
0x18001552a  mov     rcx, [rsp+78h+lpKeyName]
0x180015532  lea     r13d, [rax+1]
0x180015536  mov     rax, [rsp+78h+arg_10]
0x18001553e  mov     ebp, edi
0x180015540  and     ebp, 200h
0x180015546  jnz     short loc_180015556
0x180015548  bt      edi, 0Dh
0x18001554c  jnb     loc_180015824
0x180015552  mov     rcx, [rbx+0Ch]; dwElementID
0x180015556  test    rcx, rcx
0x180015559  jnz     short loc_18001559C
0x18001555b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015562  lea     rax, WPP_GLOBAL_Control
0x180015569  cmp     rcx, rax
0x18001556c  jz      short loc_180015592
0x18001556e  test    dword ptr [rcx+1Ch], 400000h
0x180015575  jz      short loc_180015592
0x180015577  cmp     byte ptr [rcx+19h], 1
0x18001557b  jb      short loc_180015592
0x18001557d  mov     rcx, [rcx+10h]
0x180015581  lea     r8, WPP_cea7a9ba714133be50a5a9dd0a573e7f_Traceguids
0x180015588  mov     edx, 29h ; ')'
0x18001558d  call    WPP_SF_
0x180015592  mov     eax, 107h
0x180015597  jmp     loc_180015829
0x18001559c  mov     r15d, edi
0x18001559f  and     r15d, 400h
0x1800155a6  bt      edi, 0Bh
0x1800155aa  jnb     short loc_1800155B7
0x1800155ac  mov     rdx, [rbx+0Ch]; lpstrType
0x1800155b0  call    mciGetDeviceIDFromElementIDW
0x1800155b5  jmp     short loc_1800155C9
0x1800155b7  test    r15d, r15d
0x1800155ba  jz      short loc_1800155C0
0x1800155bc  mov     rcx, [rbx+1Ch]; lpString2
0x1800155c0  mov     rdx, [rax+10h]; void *
0x1800155c4  call    ?mciGetDeviceIDInternal@@YAIPEBGPEAX@Z; mciGetDeviceIDInternal(ushort const *,void *)
0x1800155c9  test    eax, eax
0x1800155cb  jz      short loc_1800155E1
0x1800155cd  neg     r15d
0x1800155d0  mov     ebp, 109h
0x1800155d5  sbb     eax, eax
0x1800155d7  and     eax, 18h
0x1800155da  add     eax, ebp
0x1800155dc  jmp     loc_180015829
0x1800155e1  test    r13d, r13d
0x1800155e4  jnz     loc_1800157A2
0x1800155ea  test    ebp, ebp
0x1800155ec  mov     ebp, 2000h
0x1800155f1  jz      short loc_180015644
0x1800155f3  test    ebp, edi
0x1800155f5  jnz     short loc_180015644
0x1800155f7  mov     ecx, 0A0h; Size
0x1800155fc  call    winmmAlloc
0x180015601  mov     rsi, rax
0x180015604  test    rax, rax
0x180015607  jz      short loc_180015661
0x180015609  mov     r15, [rsp+78h+lpKeyName]
0x180015611  mov     rdx, rax; lpReturnedString
0x180015614  mov     rcx, r15; lpKeyName
0x180015617  call    mciExtractDeviceType
0x18001561c  test    eax, eax
0x18001561e  jz      short loc_180015628
0x180015620  mov     [rbx+0Ch], rsi
0x180015624  or      edi, ebp
0x180015626  jmp     short loc_180015693
0x180015628  mov     rcx, cs:hHeap; hHeap
0x18001562f  mov     r8, rsi; lpMem
0x180015632  xor     edx, edx; dwFlags
0x180015634  call    cs:__imp_HeapFree
0x18001563a  mov     eax, 119h
0x18001563f  jmp     loc_180015829
0x180015644  mov     eax, edi
0x180015646  and     eax, 2200h
0x18001564b  cmp     eax, ebp
0x18001564d  jnz     short loc_18001568B
0x18001564f  mov     ecx, 0A0h; Size
0x180015654  call    winmmAlloc
0x180015659  mov     rsi, rax
0x18001565c  test    rax, rax
0x18001565f  jnz     short loc_18001566B
0x180015661  mov     eax, 108h
0x180015666  jmp     loc_180015829
0x18001566b  mov     rcx, [rbx+0Ch]; lpKeyName
0x18001566f  mov     rdx, rsi; lpReturnedString
0x180015672  call    mciExtractDeviceType
0x180015677  mov     rcx, [rbx+0Ch]
0x18001567b  test    eax, eax
0x18001567d  jz      short loc_1800156C5
0x18001567f  bts     edi, 9
0x180015683  mov     [rbx+14h], rcx
0x180015687  mov     [rbx+0Ch], rsi
0x18001568b  mov     r15, [rsp+78h+lpKeyName]
0x180015693  mov     rbp, [rsp+78h+arg_10]
0x18001569b  mov     edx, 400h
0x1800156a0  test    edx, edi
0x1800156a2  jnz     loc_1800157B2
0x1800156a8  bt      edi, 9
0x1800156ac  jnb     loc_18001578B
0x1800156b2  bt      edi, 0Bh
0x1800156b6  jb      loc_1800157B2
0x1800156bc  mov     rax, [rbx+14h]
0x1800156c0  jmp     loc_18001578F
0x1800156c5  mov     [rsp+78h+var_50], rcx
0x1800156ca  mov     r8, rsi; lpMem
0x1800156cd  mov     rcx, cs:hHeap; hHeap
0x1800156d4  xor     edx, edx; dwFlags
0x1800156d6  call    cs:__imp_HeapFree
0x1800156dc  mov     edx, 21h ; '!'
0x1800156e1  mov     [rsp+78h+var_58], r12
0x1800156e6  lea     r8, [rsp+78h+var_58]
0x1800156eb  lea     rcx, [rsp+78h+var_50]
0x1800156f0  lea     r9d, [rdx-20h]
0x1800156f4  call    mciEatToken
0x1800156f9  mov     rsi, [rsp+78h+var_58]
0x1800156fe  mov     ebp, eax
0x180015700  test    eax, eax
0x180015702  jnz     short loc_180015781
0x180015704  test    rsi, rsi
0x180015707  jz      short loc_18001568B
0x180015709  xor     edx, edx
0x18001570b  lea     r9d, [rax+1]
0x18001570f  lea     r8, [rsp+78h+lpMem]
0x180015717  lea     rcx, [rsp+78h+var_50]
0x18001571c  call    mciEatToken
0x180015721  mov     r14, [rsp+78h+lpMem]
0x180015729  xor     ecx, ecx
0x18001572b  mov     ebp, eax
0x18001572d  test    eax, eax
0x18001572f  jnz     short loc_18001575E
0x180015731  mov     rbp, [rsp+78h+arg_10]
0x180015739  test    r14, r14
0x18001573c  jz      short loc_180015774
0x18001573e  cmp     [r14], cx
0x180015742  jz      short loc_180015774
0x180015744  test    r15d, r15d
0x180015747  jnz     short loc_180015768
0x180015749  mov     rdx, [rbp+10h]; void *
0x18001574d  mov     rcx, r14; lpString2
0x180015750  call    ?mciGetDeviceIDInternal@@YAIPEBGPEAX@Z; mciGetDeviceIDInternal(ushort const *,void *)
0x180015755  test    eax, eax
0x180015757  jz      short loc_180015768
0x180015759  mov     ebp, 109h
0x18001575e  mov     r15, [rsp+78h+lpKeyName]
0x180015766  jmp     short loc_1800157C4
0x180015768  mov     [rbx+14h], r14
0x18001576c  bts     edi, 9
0x180015770  mov     [rbx+0Ch], rsi
0x180015774  mov     r15, [rsp+78h+lpKeyName]
0x18001577c  jmp     loc_18001569B
0x180015781  mov     r15, [rsp+78h+lpKeyName]
0x180015789  jmp     short loc_1800157DB
0x18001578b  mov     rax, [rbx+0Ch]
0x18001578f  test    rax, rax
0x180015792  jz      short loc_1800157B2
0x180015794  mov     [rbx+1Ch], rax
0x180015798  or      edi, edx
0x18001579a  mov     r12d, 1
0x1800157a0  jmp     short loc_1800157B2
0x1800157a2  mov     rbp, [rsp+78h+arg_10]
0x1800157aa  mov     r15, [rsp+78h+lpKeyName]
0x1800157b2  mov     r9d, r12d; int
0x1800157b5  mov     r8, rbp; struct MCI_INTERNAL_OPEN_INFO *
0x1800157b8  mov     rdx, rbx; struct tagMCI_OPEN_PARMSW *
0x1800157bb  mov     ecx, edi; unsigned int
0x1800157bd  call    ?mciLoadDevice@@YAKKPEAUtagMCI_OPEN_PARMSW@@PEAUMCI_INTERNAL_OPEN_INFO@@H@Z; mciLoadDevice(ulong,tagMCI_OPEN_PARMSW *,MCI_INTERNAL_OPEN_INFO *,int)
0x1800157c2  mov     ebp, eax
0x1800157c4  test    r14, r14
0x1800157c7  jz      short loc_1800157DB
0x1800157c9  mov     rcx, cs:hHeap; hHeap
0x1800157d0  mov     r8, r14; lpMem
0x1800157d3  xor     edx, edx; dwFlags
0x1800157d5  call    cs:__imp_HeapFree
0x1800157db  test    rsi, rsi
0x1800157de  jz      short loc_1800157F2
0x1800157e0  mov     rcx, cs:hHeap; hHeap
0x1800157e7  mov     r8, rsi; lpMem
0x1800157ea  xor     edx, edx; dwFlags
0x1800157ec  call    cs:__imp_HeapFree
0x1800157f2  test    r13d, r13d
0x1800157f5  jz      short loc_18001580A
0x1800157f7  mov     r8, [rbx+0Ch]; lpMem
0x1800157fb  xor     edx, edx; dwFlags
0x1800157fd  mov     rcx, cs:hHeap; hHeap
0x180015804  call    cs:__imp_HeapFree
0x18001580a  mov     rax, [rsp+78h+var_48]
0x18001580f  mov     [rbx+0Ch], rax
0x180015813  mov     rax, [rsp+78h+var_40]
0x180015818  mov     [rbx+1Ch], rax
0x18001581c  mov     eax, ebp
0x18001581e  mov     [rbx+14h], r15
0x180015822  jmp     short loc_180015829
0x180015824  mov     eax, 111h
0x180015829  mov     rbx, [rsp+78h+arg_0]
0x180015831  add     rsp, 40h
0x180015835  pop     r15
0x180015837  pop     r14
0x180015839  pop     r13
0x18001583b  pop     r12
0x18001583d  pop     rdi
0x18001583e  pop     rsi
0x18001583f  pop     rbp
0x180015840  retn
```
