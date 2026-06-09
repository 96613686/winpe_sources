# CExtensionExclusionsPolicy::Normalize(ushort *,unsigned __int64,ushort const *)

- ea: `0x180010544`
- end: `0x18001067a`
- name: `?Normalize@CExtensionExclusionsPolicy@@SAJPEAG_KPEBG@Z`
- size: `310`
- prototype: `__int64 __fastcall(LPCWSTR lpSrcStr, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x18000fed8`
- `0x180010034`

## callees

- `0x1800094f0`
- `0x180010544`
- `0x180010b4c`
- `0x180010c48`

## import_xrefs

- `SHLWAPI!PathRemoveBlanksW` at `0x180010619`
- `SHLWAPI!PathRemoveBlanksW` at `0x180010619`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180010661`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180010661`

## pseudocode

```c
__int64 __fastcall CExtensionExclusionsPolicy::Normalize(wchar_t *lpSrcStr, size_t a2, const unsigned __int16 *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rdx
  int v7; // ebx
  HRESULT v8; // edx
  unsigned __int64 v9; // rbp
  unsigned __int16 *v10; // rcx
  LPWSTR lpDestStr; // [rsp+20h] [rbp-58h]
  unsigned int cchDest; // [rsp+28h] [rbp-50h]
  unsigned __int64 v14[9]; // [rsp+30h] [rbp-48h] BYREF
  size_t pcchNewDestLength; // [rsp+88h] [rbp+10h] BYREF

  pcchNewDestLength = a2;
  v3 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a3[v5] );
  if ( (unsigned __int64)(v5 + 3) <= 0x106 )
  {
    if ( v5 )
    {
      pcchNewDestLength = 0;
      v8 = StringCopyWorkerW_0(lpSrcStr, 0x106u, &pcchNewDestLength, L";", (size_t)lpDestStr);
      v9 = 262 - pcchNewDestLength;
      if ( ((int)(v8 + 0x80000000) < 0 || v8 == -2147024774)
        && (v14[0] = 262 - pcchNewDestLength,
            v10 = &lpSrcStr[pcchNewDestLength],
            pcchNewDestLength = (size_t)v10,
            v8 >= 0) )
      {
        v7 = StringCchCatExW(v10, v9, a3, (unsigned __int16 **)&pcchNewDestLength, v14, cchDest);
        if ( v7 >= 0 )
        {
          PathRemoveBlanksW(lpSrcStr + 1);
          v7 = StringCchCatW((unsigned __int16 *)pcchNewDestLength, v14[0], L";");
          if ( v7 >= 0 )
          {
            do
              ++v3;
            while ( lpSrcStr[v3] );
            LCMapStringW(0x800u, 0x200u, lpSrcStr, v3, lpSrcStr, v3);
          }
        }
      }
      else
      {
        return (unsigned int)v8;
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return (unsigned int)-2147024774;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180010544  mov     [rsp+pcchNewDestLength], rdx
0x180010549  push    rbx
0x18001054a  push    rbp
0x18001054b  push    rsi
0x18001054c  push    rdi
0x18001054d  push    r14
0x18001054f  push    r15
0x180010551  sub     rsp, 48h
0x180010555  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180010559  mov     r14, r8
0x18001055c  mov     rdx, rdi
0x18001055f  xor     r15d, r15d
0x180010562  mov     rsi, rcx
0x180010565  inc     rdx
0x180010568  cmp     [r8+rdx*2], r15w
0x18001056d  jnz     short loc_180010565
0x18001056f  lea     rax, [rdx+3]
0x180010573  mov     ebp, 106h
0x180010578  cmp     rax, rbp
0x18001057b  jbe     short loc_180010587
0x18001057d  mov     ebx, 8007007Ah
0x180010582  jmp     loc_18001066B
0x180010587  test    rdx, rdx
0x18001058a  jnz     short loc_180010596
0x18001058c  mov     ebx, 80070057h
0x180010591  jmp     loc_18001066B
0x180010596  lea     r9, pszSrc; ";"
0x18001059d  mov     [rsp+78h+pcchNewDestLength], r15
0x1800105a5  lea     r8, [rsp+78h+pcchNewDestLength]; pcchNewDestLength
0x1800105ad  mov     rdx, rbp; cchDest
0x1800105b0  call    StringCopyWorkerW_0
0x1800105b5  mov     rcx, [rsp+78h+pcchNewDestLength]
0x1800105bd  mov     r8d, 80000000h
0x1800105c3  mov     edx, eax
0x1800105c5  sub     rbp, rcx
0x1800105c8  add     eax, r8d
0x1800105cb  test    r8d, eax
0x1800105ce  jnz     short loc_1800105DD
0x1800105d0  mov     ebx, 8007007Ah
0x1800105d5  cmp     edx, ebx
0x1800105d7  jnz     loc_180010669
0x1800105dd  mov     [rsp+78h+var_48], rbp
0x1800105e2  lea     rcx, [rsi+rcx*2]; unsigned __int16 *
0x1800105e6  mov     [rsp+78h+pcchNewDestLength], rcx
0x1800105ee  test    edx, edx
0x1800105f0  js      short loc_180010669
0x1800105f2  lea     rax, [rsp+78h+var_48]
0x1800105f7  mov     r8, r14; unsigned __int16 *
0x1800105fa  lea     r9, [rsp+78h+pcchNewDestLength]; unsigned __int16 **
0x180010602  mov     [rsp+78h+lpDestStr], rax; unsigned __int64 *
0x180010607  mov     rdx, rbp; unsigned __int64
0x18001060a  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001060f  mov     ebx, eax
0x180010611  test    eax, eax
0x180010613  js      short loc_18001066B
0x180010615  lea     rcx, [rsi+2]; pszPath
0x180010619  call    cs:__imp_PathRemoveBlanksW
0x18001061f  mov     rdx, [rsp+78h+var_48]; unsigned __int64
0x180010624  lea     r8, pszSrc; ";"
0x18001062b  mov     rcx, [rsp+78h+pcchNewDestLength]; unsigned __int16 *
0x180010633  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010638  mov     ebx, eax
0x18001063a  test    eax, eax
0x18001063c  js      short loc_18001066B
0x18001063e  inc     rdi
0x180010641  cmp     [rsi+rdi*2], r15w
0x180010646  jnz     short loc_18001063E
0x180010648  mov     [rsp+78h+cchDest], edi; cchDest
0x18001064c  mov     r9d, edi; cchSrc
0x18001064f  mov     r8, rsi; lpSrcStr
0x180010652  mov     [rsp+78h+lpDestStr], rsi; lpDestStr
0x180010657  mov     edx, 200h; dwMapFlags
0x18001065c  mov     ecx, 800h; Locale
0x180010661  call    cs:__imp_LCMapStringW
0x180010667  jmp     short loc_18001066B
0x180010669  mov     ebx, edx
0x18001066b  mov     eax, ebx
0x18001066d  add     rsp, 48h
0x180010671  pop     r15
0x180010673  pop     r14
0x180010675  pop     rdi
0x180010676  pop     rsi
0x180010677  pop     rbp
0x180010678  pop     rbx
0x180010679  retn
```
