# CSubscriptionItem::ReadWithAlloc(HKEY__ *,ushort const *,uchar * *,ulong *)

- ea: `0x1800163a0`
- end: `0x1800164b2`
- name: `?ReadWithAlloc@CSubscriptionItem@@QEAAJPEAUHKEY__@@PEBGPEAPEAEPEAK@Z`
- size: `274`
- prototype: `int(CSubscriptionItem *__hidden this, HKEY, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180016270`

## callees

- `0x1800163a0`
- `0x180019948`
- `0x18001ba08`
- `0x18001ba40`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180016491`
- `ADVAPI32!RegCloseKey` at `0x180016491`
- `ADVAPI32!RegQueryValueExW` at `0x18001641f`
- `ADVAPI32!RegQueryValueExW` at `0x18001645a`
- `ADVAPI32!RegQueryValueExW` at `0x18001641f`
- `ADVAPI32!RegQueryValueExW` at `0x18001645a`

## pseudocode

```c
__int64 __fastcall CSubscriptionItem::ReadWithAlloc(
        CSubscriptionItem *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int8 **a4,
        LPDWORD a5)
{
  HKEY v6; // rcx
  unsigned int v10; // edi
  BYTE *lpData; // rax
  DWORD *lpcbData; // rsi
  unsigned __int8 *v13; // rbx
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF

  hKey = a2;
  v6 = a2;
  v10 = -2147467259;
  if ( !a2 )
  {
    if ( !OpenItemKey((const struct _GUID *)((char *)this + 12), 0, 0x20019u, &hKey) )
      return v10;
    v6 = hKey;
  }
  Type = 0;
  cbData = 0;
  if ( !RegQueryValueExW(v6, a3, 0, &Type, 0, &cbData) )
  {
    lpData = (BYTE *)operator new(cbData);
    lpcbData = a5;
    v13 = lpData;
    *a5 = cbData;
    if ( lpData )
    {
      if ( !RegQueryValueExW(hKey, a3, 0, &Type, lpData, lpcbData) && cbData == *lpcbData && Type == 3 )
      {
        *a4 = v13;
        v10 = 0;
      }
      else
      {
        operator delete(v13);
      }
    }
    else
    {
      v10 = -2147024882;
    }
  }
  if ( !a2 )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x1800163a0  mov     [rsp-28h+arg_0], rbx
0x1800163a5  mov     [rsp-28h+arg_10], rsi
0x1800163aa  push    rbp
0x1800163ab  push    rdi
0x1800163ac  push    r12
0x1800163ae  push    r14
0x1800163b0  push    r15
0x1800163b2  mov     rbp, rsp
0x1800163b5  sub     rsp, 40h
0x1800163b9  mov     [rbp+hKey], rdx
0x1800163bd  mov     rax, rcx
0x1800163c0  mov     rcx, rdx
0x1800163c3  mov     r12, r9
0x1800163c6  mov     r15, r8
0x1800163c9  mov     r14, rdx
0x1800163cc  mov     edi, 80004005h
0x1800163d1  test    rdx, rdx
0x1800163d4  jnz     short loc_1800163F5
0x1800163d6  lea     rcx, [rax+0Ch]; struct _GUID *
0x1800163da  mov     r8d, 20019h; unsigned int
0x1800163e0  lea     r9, [rbp+hKey]; HKEY *
0x1800163e4  call    ?OpenItemKey@@YAHPEBU_GUID@@HKPEAPEAUHKEY__@@@Z; OpenItemKey(_GUID const *,int,ulong,HKEY__ * *)
0x1800163e9  test    eax, eax
0x1800163eb  jz      loc_180016497
0x1800163f1  mov     rcx, [rbp+hKey]; hKey
0x1800163f5  lea     rax, [rbp+cbData]
0x1800163f9  mov     [rbp+Type], 0
0x180016400  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180016405  lea     r9, [rbp+Type]; lpType
0x180016409  xor     r8d, r8d; lpReserved
0x18001640c  mov     [rsp+40h+lpData], 0; lpData
0x180016415  mov     rdx, r15; lpValueName
0x180016418  mov     [rbp+cbData], 0
0x18001641f  call    cs:__imp_RegQueryValueExW
0x180016425  test    eax, eax
0x180016427  jnz     short loc_180016488
0x180016429  mov     ecx, [rbp+cbData]; dwBytes
0x18001642c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016431  mov     rsi, [rbp+arg_20]
0x180016435  mov     rbx, rax
0x180016438  mov     ecx, [rbp+cbData]
0x18001643b  mov     [rsi], ecx
0x18001643d  test    rax, rax
0x180016440  jz      short loc_180016483
0x180016442  mov     rcx, [rbp+hKey]; hKey
0x180016446  lea     r9, [rbp+Type]; lpType
0x18001644a  mov     [rsp+40h+lpcbData], rsi; lpcbData
0x18001644f  xor     r8d, r8d; lpReserved
0x180016452  mov     rdx, r15; lpValueName
0x180016455  mov     [rsp+40h+lpData], rax; lpData
0x18001645a  call    cs:__imp_RegQueryValueExW
0x180016460  test    eax, eax
0x180016462  jnz     short loc_180016479
0x180016464  mov     eax, [rsi]
0x180016466  cmp     [rbp+cbData], eax
0x180016469  jnz     short loc_180016479
0x18001646b  cmp     [rbp+Type], 3
0x18001646f  jnz     short loc_180016479
0x180016471  mov     [r12], rbx
0x180016475  xor     edi, edi
0x180016477  jmp     short loc_180016488
0x180016479  mov     rcx, rbx; lpMem
0x18001647c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016481  jmp     short loc_180016488
0x180016483  mov     edi, 8007000Eh
0x180016488  test    r14, r14
0x18001648b  jnz     short loc_180016497
0x18001648d  mov     rcx, [rbp+hKey]; hKey
0x180016491  call    cs:__imp_RegCloseKey
0x180016497  lea     r11, [rsp+40h+var_s0]
0x18001649c  mov     eax, edi
0x18001649e  mov     rbx, [r11+30h]
0x1800164a2  mov     rsi, [r11+40h]
0x1800164a6  mov     rsp, r11
0x1800164a9  pop     r15
0x1800164ab  pop     r14
0x1800164ad  pop     r12
0x1800164af  pop     rdi
0x1800164b0  pop     rbp
0x1800164b1  retn
```
