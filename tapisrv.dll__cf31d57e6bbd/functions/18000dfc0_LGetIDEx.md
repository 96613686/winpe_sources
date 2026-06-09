# LGetIDEx

- ea: `0x18000dfc0`
- end: `0x18000e293`
- name: `LGetIDEx`
- size: `723`
- prototype: `__int64 __fastcall(int, _DWORD *, unsigned int, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180028100`

## callees

- `0x1800072e4`
- `0x18000d980`
- `0x18000dfc0`
- `0x18001c854`
- `0x18001f734`
- `0x18002c8d4`
- `0x18003dc84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e09d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e0b5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e0cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e0e5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e0fd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e09d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e0b5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e0cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e0e5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e0fd`
- `KERNEL32!HeapAlloc` at `0x18000e02b`
- `KERNEL32!HeapAlloc` at `0x18000e02b`

## string_xrefs

- `0x18000e039`: `LGetIDEx: failed to allocate DeviceClassCopy`

## pseudocode

```c
__int64 __fastcall LGetIDEx(int a1, _DWORD *a2, unsigned int a3, _DWORD *a4, _DWORD *a5)
{
  __int64 v5; // rdi
  __int64 result; // rax
  const wchar_t *v10; // r14
  __int64 v11; // rdi
  __int64 v12; // rax
  size_t v13; // r15
  wchar_t *v14; // rbp
  wchar_t *v15; // r15
  __int64 v16; // rax
  const wchar_t *v17; // r14
  __int64 v18; // rcx
  size_t v19; // rsi
  size_t v20; // rdi
  int v21; // eax
  int v22; // r11d
  int v23; // eax
  wchar_t *v24; // rcx
  const wchar_t *v25; // rax
  const wchar_t *v26; // r11
  size_t v27; // rdi
  int v28; // eax
  int v29; // eax

  v5 = (unsigned int)a2[7];
  result = IsBadStringParam(a3, (__int64)a4, a2[7]);
  if ( (_DWORD)result )
  {
    *a2 = -2147483576;
    return result;
  }
  v10 = (const wchar_t *)((char *)a4 + v5);
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( v10[v12] );
  v13 = 2 * v12 + 2;
  v14 = (wchar_t *)HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)(2 * v12 + 2));
  if ( !v14 )
  {
    TRACELogPrint(65538, "LGetIDEx: failed to allocate DeviceClassCopy");
    *a2 = -2147483580;
  }
  StringCbCopyW(v14, v13, v10);
  LGetID(a1, (__int64)a5);
  if ( !*a2 && a4[1] <= *a4 )
  {
    if ( !(unsigned int)_o__wcsicmp(v14, L"wave/in")
      || !(unsigned int)_o__wcsicmp(v14, L"wave/out")
      || !(unsigned int)_o__wcsicmp(v14, L"midi/in")
      || !(unsigned int)_o__wcsicmp(v14, L"midi/out") )
    {
      v25 = (const wchar_t *)WaveDeviceIdToStringId((HMIDIOUT)*(unsigned int *)((char *)a4 + (unsigned int)a4[5]));
      v26 = v25;
      if ( !v25 )
      {
        TRACELogPrint(65538, "LGetIDEx:  WaveDeviceIdToStringId failed");
        *a2 = -2147483576;
        return ServerFree(v14);
      }
      do
        ++v11;
      while ( v25[v11] );
      v27 = 2 * v11 + 2;
      if ( (unsigned int)(*a4 - a4[2] + 4) < v27 )
      {
        a4[1] = v27;
      }
      else
      {
        StringCbCopyW((STRSAFE_LPWSTR)((char *)a4 + (unsigned int)a4[5]), v27, v25);
        v28 = a4[2] - 4;
        a4[4] = v27;
        v29 = v27 + v28;
        a4[1] = v29;
        a4[2] = v29;
        *a5 = v29 + 60;
      }
      v24 = (wchar_t *)v26;
      goto LABEL_31;
    }
    if ( !(unsigned int)_o__wcsicmp(v14, L"wave/in/out") )
    {
      v15 = (wchar_t *)WaveDeviceIdToStringId((HMIDIOUT)*(unsigned int *)((char *)a4 + (unsigned int)a4[5]));
      v16 = WaveDeviceIdToStringId((HMIDIOUT)*(unsigned int *)((char *)a4 + (unsigned int)a4[5] + 4));
      v17 = (const wchar_t *)v16;
      if ( v15 && v16 )
      {
        v18 = -1;
        do
          ++v18;
        while ( v15[v18] );
        v19 = 2 * v18 + 2;
        do
          ++v11;
        while ( *(_WORD *)(v16 + 2 * v11) );
        v20 = 2 * v11 + 2;
        if ( (unsigned int)(*a4 - a4[2] + 8) < v20 + v19 )
        {
          a4[1] = v20 + v19;
        }
        else
        {
          StringCbCopyW((STRSAFE_LPWSTR)((char *)a4 + (unsigned int)a4[5]), v19, v15);
          StringCbCopyW((STRSAFE_LPWSTR)((char *)a4 + v19 + (unsigned int)a4[5]), v20, v17);
          v21 = a4[2] - 8;
          a4[4] = v22;
          v23 = v20 + v19 + v21;
          a4[1] = v23;
          a4[2] = v23;
          *a5 = v23 + 60;
        }
      }
      else
      {
        TRACELogPrint(65538, "LGetIDEx:  WaveDeviceIdToStringId failed");
        *a2 = -2147483576;
      }
      ServerFree(v15);
      v24 = (wchar_t *)v17;
LABEL_31:
      ServerFree(v24);
    }
  }
  return ServerFree(v14);
}

```

## disassembly

```asm
0x18000dfc0  push    rbx
0x18000dfc2  push    rbp
0x18000dfc3  push    rsi
0x18000dfc4  push    rdi
0x18000dfc5  push    r12
0x18000dfc7  push    r13
0x18000dfc9  push    r14
0x18000dfcb  push    r15
0x18000dfcd  sub     rsp, 38h
0x18000dfd1  mov     edi, [rdx+1Ch]
0x18000dfd4  mov     r12d, r8d
0x18000dfd7  mov     rsi, rdx
0x18000dfda  mov     r13, rcx
0x18000dfdd  mov     r8d, edi
0x18000dfe0  mov     ecx, r12d
0x18000dfe3  mov     rdx, r9
0x18000dfe6  mov     rbx, r9
0x18000dfe9  call    IsBadStringParam
0x18000dfee  xor     ecx, ecx
0x18000dff0  test    eax, eax
0x18000dff2  jz      short loc_18000DFFF
0x18000dff4  mov     dword ptr [rsi], 80000048h
0x18000dffa  jmp     loc_18000E282
0x18000dfff  lea     r14, [rbx+rdi]
0x18000e003  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000e007  mov     rax, rdi
0x18000e00a  inc     rax
0x18000e00d  cmp     [r14+rax*2], cx
0x18000e012  jnz     short loc_18000E00A
0x18000e014  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18000e01b  lea     r15, ds:2[rax*2]
0x18000e023  mov     r8d, r15d; dwBytes
0x18000e026  mov     edx, 8; dwFlags
0x18000e02b  call    cs:__imp_HeapAlloc
0x18000e031  mov     rbp, rax
0x18000e034  test    rax, rax
0x18000e037  jnz     short loc_18000E050
0x18000e039  lea     rdx, aLgetidexFailed; "LGetIDEx: failed to allocate DeviceClas"...
0x18000e040  mov     ecx, 10002h
0x18000e045  call    TRACELogPrint
0x18000e04a  mov     dword ptr [rsi], 80000044h
0x18000e050  mov     r8, r14; pszSrc
0x18000e053  mov     rdx, r15; cbDest
0x18000e056  mov     rcx, rbp; pszDest
0x18000e059  call    StringCbCopyW
0x18000e05e  mov     r14, [rsp+78h+arg_20]
0x18000e066  mov     r9, rbx
0x18000e069  mov     r8d, r12d
0x18000e06c  mov     [rsp+78h+var_58], r14; __int64
0x18000e071  mov     rdx, rsi
0x18000e074  mov     rcx, r13; int
0x18000e077  call    LGetID
0x18000e07c  xor     r12d, r12d
0x18000e07f  cmp     [rsi], r12d
0x18000e082  jnz     loc_18000E27A
0x18000e088  mov     eax, [rbx]
0x18000e08a  cmp     [rbx+4], eax
0x18000e08d  ja      loc_18000E27A
0x18000e093  lea     rdx, aWaveIn; "wave/in"
0x18000e09a  mov     rcx, rbp
0x18000e09d  call    cs:__imp__o__wcsicmp
0x18000e0a3  test    eax, eax
0x18000e0a5  jz      loc_18000E1F7
0x18000e0ab  lea     rdx, aWaveOut; "wave/out"
0x18000e0b2  mov     rcx, rbp
0x18000e0b5  call    cs:__imp__o__wcsicmp
0x18000e0bb  test    eax, eax
0x18000e0bd  jz      loc_18000E1F7
0x18000e0c3  lea     rdx, aMidiIn; "midi/in"
0x18000e0ca  mov     rcx, rbp
0x18000e0cd  call    cs:__imp__o__wcsicmp
0x18000e0d3  test    eax, eax
0x18000e0d5  jz      loc_18000E1F7
0x18000e0db  lea     rdx, aMidiOut; "midi/out"
0x18000e0e2  mov     rcx, rbp
0x18000e0e5  call    cs:__imp__o__wcsicmp
0x18000e0eb  test    eax, eax
0x18000e0ed  jz      loc_18000E1F7
0x18000e0f3  lea     rdx, aWaveInOut; "wave/in/out"
0x18000e0fa  mov     rcx, rbp
0x18000e0fd  call    cs:__imp__o__wcsicmp
0x18000e103  test    eax, eax
0x18000e105  jnz     loc_18000E27A
0x18000e10b  mov     ecx, [rbx+14h]
0x18000e10e  lea     rdx, aWaveIn; "wave/in"
0x18000e115  mov     ecx, [rcx+rbx]; hmo
0x18000e118  call    WaveDeviceIdToStringId
0x18000e11d  mov     ecx, [rbx+14h]
0x18000e120  lea     rdx, aWaveOut; "wave/out"
0x18000e127  mov     r15, rax
0x18000e12a  mov     ecx, [rcx+rbx+4]; hmo
0x18000e12e  call    WaveDeviceIdToStringId
0x18000e133  mov     r14, rax
0x18000e136  test    r15, r15
0x18000e139  jz      loc_18000E1D3
0x18000e13f  test    rax, rax
0x18000e142  jz      loc_18000E1D3
0x18000e148  mov     rcx, rdi
0x18000e14b  inc     rcx
0x18000e14e  cmp     [r15+rcx*2], r12w
0x18000e153  jnz     short loc_18000E14B
0x18000e155  lea     rsi, ds:2[rcx*2]
0x18000e15d  inc     rdi
0x18000e160  cmp     [rax+rdi*2], r12w
0x18000e165  jnz     short loc_18000E15D
0x18000e167  mov     ecx, [rbx]
0x18000e169  lea     rdi, ds:2[rdi*2]
0x18000e171  sub     ecx, [rbx+8]
0x18000e174  lea     rax, [rdi+rsi]
0x18000e178  add     ecx, 8
0x18000e17b  lea     r11d, [rdi+rsi]
0x18000e17f  cmp     rcx, rax
0x18000e182  jb      short loc_18000E1CD
0x18000e184  mov     ecx, [rbx+14h]
0x18000e187  mov     r8, r15; pszSrc
0x18000e18a  add     rcx, rbx; pszDest
0x18000e18d  mov     rdx, rsi; cbDest
0x18000e190  call    StringCbCopyW
0x18000e195  mov     ecx, [rbx+14h]
0x18000e198  mov     r8, r14; pszSrc
0x18000e19b  add     rcx, rsi
0x18000e19e  mov     rdx, rdi; cbDest
0x18000e1a1  add     rcx, rbx; pszDest
0x18000e1a4  call    StringCbCopyW
0x18000e1a9  mov     eax, [rbx+8]
0x18000e1ac  lea     ecx, [rdi+rsi]
0x18000e1af  add     eax, 0FFFFFFF8h
0x18000e1b2  mov     [rbx+10h], r11d
0x18000e1b6  add     eax, ecx
0x18000e1b8  mov     rcx, [rsp+78h+arg_20]
0x18000e1c0  mov     [rbx+4], eax
0x18000e1c3  mov     [rbx+8], eax
0x18000e1c6  add     eax, 3Ch ; '<'
0x18000e1c9  mov     [rcx], eax
0x18000e1cb  jmp     short loc_18000E1EA
0x18000e1cd  mov     [rbx+4], r11d
0x18000e1d1  jmp     short loc_18000E1EA
0x18000e1d3  lea     rdx, aLgetidexWavede; "LGetIDEx:  WaveDeviceIdToStringId faile"...
0x18000e1da  mov     ecx, 10002h
0x18000e1df  call    TRACELogPrint
0x18000e1e4  mov     dword ptr [rsi], 80000048h
0x18000e1ea  mov     rcx, r15; lpMem
0x18000e1ed  call    ServerFree
0x18000e1f2  mov     rcx, r14
0x18000e1f5  jmp     short loc_18000E25C
0x18000e1f7  mov     ecx, [rbx+14h]
0x18000e1fa  mov     rdx, rbp
0x18000e1fd  mov     ecx, [rcx+rbx]; hmo
0x18000e200  call    WaveDeviceIdToStringId
0x18000e205  mov     r11, rax
0x18000e208  test    rax, rax
0x18000e20b  jz      short loc_18000E263
0x18000e20d  inc     rdi
0x18000e210  cmp     [rax+rdi*2], r12w
0x18000e215  jnz     short loc_18000E20D
0x18000e217  mov     eax, [rbx]
0x18000e219  lea     rdi, ds:2[rdi*2]
0x18000e221  sub     eax, [rbx+8]
0x18000e224  add     eax, 4
0x18000e227  cmp     rax, rdi
0x18000e22a  jb      short loc_18000E256
0x18000e22c  mov     ecx, [rbx+14h]
0x18000e22f  mov     r8, r11; pszSrc
0x18000e232  add     rcx, rbx; pszDest
0x18000e235  mov     rdx, rdi; cbDest
0x18000e238  call    StringCbCopyW
0x18000e23d  mov     eax, [rbx+8]
0x18000e240  add     eax, 0FFFFFFFCh
0x18000e243  mov     [rbx+10h], edi
0x18000e246  add     eax, edi
0x18000e248  mov     [rbx+4], eax
0x18000e24b  mov     [rbx+8], eax
0x18000e24e  add     eax, 3Ch ; '<'
0x18000e251  mov     [r14], eax
0x18000e254  jmp     short loc_18000E259
0x18000e256  mov     [rbx+4], edi
0x18000e259  mov     rcx, r11; lpMem
0x18000e25c  call    ServerFree
0x18000e261  jmp     short loc_18000E27A
0x18000e263  lea     rdx, aLgetidexWavede; "LGetIDEx:  WaveDeviceIdToStringId faile"...
0x18000e26a  mov     ecx, 10002h
0x18000e26f  call    TRACELogPrint
0x18000e274  mov     dword ptr [rsi], 80000048h
0x18000e27a  mov     rcx, rbp; lpMem
0x18000e27d  call    ServerFree
0x18000e282  add     rsp, 38h
0x18000e286  pop     r15
0x18000e288  pop     r14
0x18000e28a  pop     r13
0x18000e28c  pop     r12
0x18000e28e  pop     rdi
0x18000e28f  pop     rsi
0x18000e290  pop     rbp
0x18000e291  pop     rbx
0x18000e292  retn
```
