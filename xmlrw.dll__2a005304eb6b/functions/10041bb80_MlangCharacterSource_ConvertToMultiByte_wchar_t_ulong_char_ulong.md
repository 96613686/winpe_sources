# MlangCharacterSource::ConvertToMultiByte(wchar_t *,ulong,char *,ulong)

- ea: `0x10041bb80`
- end: `0x10041bc81`
- name: `?ConvertToMultiByte@MlangCharacterSource@@MEAAKPEA_WKPEADK@Z`
- size: `257`
- prototype: `unsigned int __fastcall(MlangCharacterSource *__hidden this, wchar_t *, unsigned int, char *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x100401780`
- `0x10041bb80`
- `0x100439df0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x10041bbe1`
- `ole32!CoCreateInstance` at `0x10041bbe1`

## pseudocode

```c
__int64 __fastcall MlangCharacterSource::ConvertToMultiByte(
        MlangCharacterSource *this,
        wchar_t *a2,
        int a3,
        char *a4,
        unsigned int a5)
{
  unsigned int v5; // r14d
  struct IMultiLanguage2 *v7; // rcx
  HRESULT Instance; // eax
  bool v12; // zf
  signed __int64 v14; // [rsp+60h] [rbp+8h] BYREF
  int v15; // [rsp+70h] [rbp+18h] BYREF

  v5 = *((_DWORD *)this + 62);
  v7 = s_pMultiLanguage2;
  v15 = a3;
  if ( !s_pMultiLanguage2 )
  {
    v14 = 0;
    Instance = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage2, (LPVOID *)&v14);
    v12 = Instance == 0;
    if ( Instance >= 0 )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&s_pMultiLanguage2, v14, 0) )
        (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v14 + 16LL))(v14);
      v12 = 1;
    }
    if ( !v12 )
    {
LABEL_11:
      MXRRaiseException(-1072894461);
      JUMPOUT(0x10041BC80LL);
    }
    v7 = s_pMultiLanguage2;
  }
  if ( ((unsigned int (__fastcall *)(struct IMultiLanguage2 *, char *, _QWORD, wchar_t *, int *, char *, unsigned int *))v7->lpVtbl->ConvertStringFromUnicode)(
         v7,
         (char *)this + 268,
         v5,
         a2,
         &v15,
         a4,
         &a5)
    || v15 != a3 )
  {
    goto LABEL_11;
  }
  return a5;
}

```

## disassembly

```asm
0x10041bb80  mov     r11, rsp
0x10041bb83  mov     [r11+10h], rbx
0x10041bb87  mov     [r11+20h], rbp
0x10041bb8b  push    rsi
0x10041bb8c  push    rdi
0x10041bb8d  push    r14
0x10041bb8f  sub     rsp, 40h
0x10041bb93  mov     r14d, [rcx+0F8h]
0x10041bb9a  mov     rdi, rcx
0x10041bb9d  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x10041bba4  mov     ebx, r8d
0x10041bba7  mov     eax, [rsp+58h+arg_20]
0x10041bbae  mov     rsi, r9
0x10041bbb1  mov     [rsp+58h+arg_10], ebx
0x10041bbb5  mov     rbp, rdx
0x10041bbb8  mov     [r11+28h], eax
0x10041bbbc  test    rcx, rcx
0x10041bbbf  jnz     short loc_10041BC1C
0x10041bbc1  mov     [r11+8], rcx
0x10041bbc5  lea     rax, [r11+8]
0x10041bbc9  lea     r8d, [rcx+1]; dwClsContext
0x10041bbcd  mov     [r11-38h], rax
0x10041bbd1  lea     rcx, CLSID_CMultiLanguage; rclsid
0x10041bbd8  xor     edx, edx; pUnkOuter
0x10041bbda  lea     r9, IID_IMultiLanguage2; riid
0x10041bbe1  call    cs:__imp_CoCreateInstance
0x10041bbe7  test    eax, eax
0x10041bbe9  js      short loc_10041BC13
0x10041bbeb  mov     rcx, [rsp+58h+arg_0]
0x10041bbf0  xor     eax, eax
0x10041bbf2  lock cmpxchg cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA, rcx; IMultiLanguage2 * s_pMultiLanguage2
0x10041bbfb  jz      short loc_10041BC0F
0x10041bbfd  mov     rcx, [rsp+58h+arg_0]
0x10041bc02  mov     rax, [rcx]
0x10041bc05  mov     rax, [rax+10h]
0x10041bc09  call    cs:__guard_dispatch_icall_fptr
0x10041bc0f  xor     eax, eax
0x10041bc11  test    eax, eax
0x10041bc13  jnz     short loc_10041BC76
0x10041bc15  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x10041bc1c  mov     rax, [rcx]
0x10041bc1f  lea     r8, [rsp+58h+arg_20]
0x10041bc27  mov     [rsp+58h+var_28], r8
0x10041bc2c  lea     rdx, [rdi+10Ch]
0x10041bc33  lea     r8, [rsp+58h+arg_10]
0x10041bc38  mov     [rsp+58h+var_30], rsi
0x10041bc3d  mov     [rsp+58h+var_38], r8
0x10041bc42  mov     r9, rbp
0x10041bc45  mov     rax, [rax+58h]
0x10041bc49  mov     r8d, r14d
0x10041bc4c  call    cs:__guard_dispatch_icall_fptr
0x10041bc52  test    eax, eax
0x10041bc54  jnz     short loc_10041BC76
0x10041bc56  cmp     [rsp+58h+arg_10], ebx
0x10041bc5a  jnz     short loc_10041BC76
0x10041bc5c  mov     eax, [rsp+58h+arg_20]
0x10041bc63  mov     rbx, [rsp+58h+arg_8]
0x10041bc68  mov     rbp, [rsp+58h+arg_18]
0x10041bc6d  add     rsp, 40h
0x10041bc71  pop     r14
0x10041bc73  pop     rdi
0x10041bc74  pop     rsi
0x10041bc75  retn
0x10041bc76  mov     ecx, 0C00CEE03h; int
0x10041bc7b  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
