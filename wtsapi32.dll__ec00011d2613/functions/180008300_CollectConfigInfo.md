# CollectConfigInfo

- ea: `0x180008300`
- end: `0x180008427`
- name: `CollectConfigInfo`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002d20`

## callees

- `0x180004150`
- `0x180008300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008414`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008414`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008330`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008330`

## pseudocode

```c
__int64 __fastcall CollectConfigInfo(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  unsigned int v3; // edi
  wchar_t *v7; // rax
  HRESULT v8; // eax
  __int64 v9; // r10
  DWORD v10; // ecx
  __int64 v11; // r10
  const wchar_t *v12; // r11
  __int64 v13; // r10
  const wchar_t *v14; // r11
  __int64 v15; // r10
  _DWORD *v16; // r10

  v3 = 0;
  if ( !a1 || !a3 )
  {
    v10 = -2147024809;
    goto LABEL_12;
  }
  v7 = (wchar_t *)LocalAlloc(0x40u, 0x684u);
  if ( v7 )
  {
    v8 = StringCchCopyW(v7 + 12, 0x15u, (STRSAFE_LPCWSTR)(a1 + 132));
    if ( v8 >= 0 )
    {
      v8 = StringCchCopyW((STRSAFE_LPWSTR)(v9 + 66), 0x12u, (STRSAFE_LPCWSTR)(a1 + 174));
      if ( v8 >= 0 )
      {
        v8 = StringCchCopyW((STRSAFE_LPWSTR)(v11 + 102), 0x105u, v12);
        if ( v8 >= 0 )
        {
          v8 = StringCchCopyW((STRSAFE_LPWSTR)(v13 + 624), 0x105u, v14);
          if ( v8 >= 0 )
          {
            v8 = StringCchCopyW((STRSAFE_LPWSTR)(v15 + 1146), 0x105u, (STRSAFE_LPCWSTR)(a1 + 1494));
            if ( v8 >= 0 )
            {
              v3 = 1;
              *v16 = 1;
              v16[1] = (*(_DWORD *)(a1 + 124) >> 17) & 1;
              v16[2] = (*(_DWORD *)(a1 + 124) >> 18) & 1;
              v16[3] = (*(_DWORD *)(a1 + 124) >> 29) & 1;
              v16[4] = (*(_DWORD *)(a1 + 124) >> 19) & 1;
              v16[5] = *(_DWORD *)(a1 + 1376);
              *a2 = v16;
              *a3 = 1668;
              return v3;
            }
          }
        }
      }
    }
    v10 = (unsigned __int16)v8;
LABEL_12:
    SetLastError(v10);
  }
  return v3;
}

```

## disassembly

```asm
0x180008300  push    rbx
0x180008302  push    rbp
0x180008303  push    rsi
0x180008304  push    rdi
0x180008305  push    r14
0x180008307  sub     rsp, 20h
0x18000830b  xor     edi, edi
0x18000830d  mov     rsi, r8
0x180008310  mov     r14, rdx
0x180008313  mov     rbx, rcx
0x180008316  test    rcx, rcx
0x180008319  jz      loc_18000840F
0x18000831f  test    r8, r8
0x180008322  jz      loc_18000840F
0x180008328  mov     edx, 684h; uBytes
0x18000832d  lea     ecx, [rdi+40h]; uFlags
0x180008330  call    cs:__imp_LocalAlloc
0x180008336  mov     r10, rax
0x180008339  test    rax, rax
0x18000833c  jz      loc_18000841A
0x180008342  lea     r11, [rbx+84h]
0x180008349  mov     r8, r11; pszSrc
0x18000834c  lea     rcx, [rax+18h]; pszDest
0x180008350  lea     edx, [rdi+15h]; cchDest
0x180008353  call    StringCchCopyW
0x180008358  test    eax, eax
0x18000835a  jns     short loc_180008364
0x18000835c  movzx   ecx, ax
0x18000835f  jmp     loc_180008414
0x180008364  lea     r8, [rbx+0AEh]; pszSrc
0x18000836b  mov     edx, 12h; cchDest
0x180008370  lea     rcx, [r10+42h]; pszDest
0x180008374  call    StringCchCopyW
0x180008379  test    eax, eax
0x18000837b  js      short loc_18000835C
0x18000837d  mov     ebp, 105h
0x180008382  lea     rcx, [r10+66h]; pszDest
0x180008386  mov     edx, ebp; cchDest
0x180008388  mov     r8, r11; pszSrc
0x18000838b  call    StringCchCopyW
0x180008390  test    eax, eax
0x180008392  js      short loc_18000835C
0x180008394  lea     rcx, [r10+270h]; pszDest
0x18000839b  mov     r8, r11; pszSrc
0x18000839e  mov     edx, ebp; cchDest
0x1800083a0  call    StringCchCopyW
0x1800083a5  test    eax, eax
0x1800083a7  js      short loc_18000835C
0x1800083a9  lea     r8, [rbx+5D6h]; pszSrc
0x1800083b0  mov     edx, ebp; cchDest
0x1800083b2  lea     rcx, [r10+47Ah]; pszDest
0x1800083b9  call    StringCchCopyW
0x1800083be  test    eax, eax
0x1800083c0  js      short loc_18000835C
0x1800083c2  mov     edi, 1
0x1800083c7  mov     [r10], edi
0x1800083ca  mov     eax, [rbx+7Ch]
0x1800083cd  shr     eax, 11h
0x1800083d0  and     eax, edi
0x1800083d2  mov     [r10+4], eax
0x1800083d6  mov     eax, [rbx+7Ch]
0x1800083d9  shr     eax, 12h
0x1800083dc  and     eax, edi
0x1800083de  mov     [r10+8], eax
0x1800083e2  mov     eax, [rbx+7Ch]
0x1800083e5  shr     eax, 1Dh
0x1800083e8  and     eax, edi
0x1800083ea  mov     [r10+0Ch], eax
0x1800083ee  mov     eax, [rbx+7Ch]
0x1800083f1  shr     eax, 13h
0x1800083f4  and     eax, edi
0x1800083f6  mov     [r10+10h], eax
0x1800083fa  mov     eax, [rbx+560h]
0x180008400  mov     [r10+14h], eax
0x180008404  mov     [r14], r10
0x180008407  mov     dword ptr [rsi], 684h
0x18000840d  jmp     short loc_18000841A
0x18000840f  mov     ecx, 80070057h; dwErrCode
0x180008414  call    cs:__imp_SetLastError
0x18000841a  mov     eax, edi
0x18000841c  add     rsp, 20h
0x180008420  pop     r14
0x180008422  pop     rdi
0x180008423  pop     rsi
0x180008424  pop     rbp
0x180008425  pop     rbx
0x180008426  retn
```
