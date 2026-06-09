# OpenKeyUsingCng(unsigned __int64 *,ushort const *,ushort const *,ulong,ulong,int,int *)

- ea: `0x18004a060`
- end: `0x18004a162`
- name: `?OpenKeyUsingCng@@YAKPEA_KPEBG1KKHPEAH@Z`
- size: `258`
- prototype: `unsigned int __fastcall(NCRYPT_KEY_HANDLE *phKey, LPCWSTR pszKeyName, LPCWSTR pszProviderName, DWORD dwLegacyKeySpec, unsigned int, int, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18006daac`
- `0x180078a2c`

## callees

- `0x180021da8`
- `0x18004a060`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x18004a0ba`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004a0ba`
- `ncrypt!NCryptFreeObject` at `0x18004a14d`
- `ncrypt!NCryptFreeObject` at `0x18004a14d`
- `ncrypt!NCryptOpenKey` at `0x18004a106`
- `ncrypt!NCryptOpenKey` at `0x18004a106`

## pseudocode

```c
__int64 __fastcall OpenKeyUsingCng(
        NCRYPT_KEY_HANDLE *phKey,
        LPCWSTR pszKeyName,
        LPCWSTR pszProviderName,
        DWORD dwLegacyKeySpec,
        unsigned int a5,
        int a6,
        int *a7)
{
  unsigned int v10; // esi
  unsigned int v11; // ebx
  CCipherMill *v12; // rcx
  __int64 v13; // rdx
  DWORD dwFlags; // esi
  NCRYPT_PROV_HANDLE phProvider[9]; // [rsp+30h] [rbp-48h] BYREF

  phProvider[0] = 0;
  if ( a7 )
    *a7 = 0;
  v10 = a5 | 0x40;
  if ( a6 )
    v10 = a5;
  v11 = NCryptOpenStorageProvider(phProvider, pszProviderName, 0);
  if ( v11 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 10;
LABEL_15:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_89c254830434370c9b8c7f7d2950a963_Traceguids, v11);
    }
  }
  else
  {
    dwFlags = v10 & 0xFFFFFFFE;
    if ( a7 )
      *a7 = 1;
    v11 = NCryptOpenKey(phProvider[0], phKey, pszKeyName, dwLegacyKeySpec, dwFlags);
    if ( v11 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 11;
        goto LABEL_15;
      }
    }
  }
  if ( phProvider[0] )
    NCryptFreeObject(phProvider[0]);
  return v11;
}

```

## disassembly

```asm
0x18004a060  push    rbx
0x18004a062  push    rbp
0x18004a063  push    rsi
0x18004a064  push    rdi
0x18004a065  push    r14
0x18004a067  push    r15
0x18004a069  sub     rsp, 48h
0x18004a06d  mov     rdi, [rsp+78h+arg_30]
0x18004a075  mov     ebp, r9d
0x18004a078  mov     [rsp+78h+phProvider], 0
0x18004a081  mov     rax, r8
0x18004a084  mov     r14, rdx
0x18004a087  mov     r15, rcx
0x18004a08a  test    rdi, rdi
0x18004a08d  jz      short loc_18004A095
0x18004a08f  mov     dword ptr [rdi], 0
0x18004a095  mov     esi, [rsp+78h+arg_20]
0x18004a09c  lea     rcx, [rsp+78h+phProvider]; phProvider
0x18004a0a1  or      esi, 40h
0x18004a0a4  mov     rdx, rax; pszProviderName
0x18004a0a7  cmp     [rsp+78h+arg_28], 0
0x18004a0af  cmovnz  esi, [rsp+78h+arg_20]
0x18004a0b7  xor     r8d, r8d; dwFlags
0x18004a0ba  call    cs:__imp_NCryptOpenStorageProvider
0x18004a0c0  mov     ebx, eax
0x18004a0c2  test    eax, eax
0x18004a0c4  jz      short loc_18004A0E6
0x18004a0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a0cd  lea     rax, WPP_GLOBAL_Control
0x18004a0d4  cmp     rcx, rax
0x18004a0d7  jz      short loc_18004A143
0x18004a0d9  test    byte ptr [rcx+1Ch], 1
0x18004a0dd  jz      short loc_18004A143
0x18004a0df  mov     edx, 0Ah
0x18004a0e4  jmp     short loc_18004A130
0x18004a0e6  and     esi, 0FFFFFFFEh
0x18004a0e9  test    rdi, rdi
0x18004a0ec  jz      short loc_18004A0F4
0x18004a0ee  mov     dword ptr [rdi], 1
0x18004a0f4  mov     rcx, [rsp+78h+phProvider]; hProvider
0x18004a0f9  mov     r9d, ebp; dwLegacyKeySpec
0x18004a0fc  mov     r8, r14; pszKeyName
0x18004a0ff  mov     [rsp+78h+dwFlags], esi; dwFlags
0x18004a103  mov     rdx, r15; phKey
0x18004a106  call    cs:__imp_NCryptOpenKey
0x18004a10c  mov     ebx, eax
0x18004a10e  test    eax, eax
0x18004a110  jz      short loc_18004A143
0x18004a112  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a119  lea     rax, WPP_GLOBAL_Control
0x18004a120  cmp     rcx, rax
0x18004a123  jz      short loc_18004A143
0x18004a125  test    byte ptr [rcx+1Ch], 1
0x18004a129  jz      short loc_18004A143
0x18004a12b  mov     edx, 0Bh
0x18004a130  mov     rcx, [rcx+10h]
0x18004a134  lea     r8, WPP_89c254830434370c9b8c7f7d2950a963_Traceguids
0x18004a13b  mov     r9d, ebx
0x18004a13e  call    WPP_SF_d
0x18004a143  mov     rcx, [rsp+78h+phProvider]; hObject
0x18004a148  test    rcx, rcx
0x18004a14b  jz      short loc_18004A153
0x18004a14d  call    cs:__imp_NCryptFreeObject
0x18004a153  mov     eax, ebx
0x18004a155  add     rsp, 48h
0x18004a159  pop     r15
0x18004a15b  pop     r14
0x18004a15d  pop     rdi
0x18004a15e  pop     rsi
0x18004a15f  pop     rbp
0x18004a160  pop     rbx
0x18004a161  retn
```
