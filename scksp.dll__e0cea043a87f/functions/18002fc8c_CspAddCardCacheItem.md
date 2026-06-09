# CspAddCardCacheItem

- ea: `0x18002fc8c`
- end: `0x18002fd80`
- name: `CspAddCardCacheItem`
- size: `244`
- prototype: `__int64 __fastcall(struct _CARD_CACHE_QUERY_INFO *, void *Destination)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18002cf2c`
- `0x18002f2e0`
- `0x18002fb68`
- `0x1800300a4`
- `0x180030500`

## callees

- `0x180011fd8`
- `0x18002eb6c`
- `0x18002f64c`
- `0x18002f830`
- `0x18002fc8c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002fd51`
- `msvcrt!memcpy_s` at `0x18002fd51`

## pseudocode

```c
__int64 __fastcall CspAddCardCacheItem(struct _CARD_CACHE_QUERY_INFO *a1, void *Destination)
{
  __int64 v4; // rcx
  _DWORD *v5; // rax
  unsigned int CardCacheFile; // edi
  int v7; // r9d
  bool v9; // zf
  DWORD v10; // eax
  _CRYPTOAPI_BLOB v11; // [rsp+30h] [rbp-38h] BYREF

  v4 = *(_QWORD *)a1;
  v5 = *(_DWORD **)(v4 + 8);
  if ( !v5 )
  {
    CardCacheFile = 87;
    WppTraceIndent(v4, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
        v7,
        (__int64)"pInfo->pCardState->pCardData");
    }
    return CardCacheFile;
  }
  if ( *v5 >= 6u && *(_DWORD *)(v4 + 696) == 3 && *((_DWORD *)a1 + 2) != 1 )
    return 0;
  v9 = *((_DWORD *)a1 + 3) == 0;
  *(&v11.cbData + 1) = 0;
  if ( !v9 )
  {
    if ( !*((_DWORD *)a1 + 137) )
    {
      CardCacheFile = I_CspReadCardCacheFile(
                        (struct _CARD_STATE *)v4,
                        (struct _CARD_CACHE_QUERY_INFO *)((char *)a1 + 540));
      if ( CardCacheFile )
        return CardCacheFile;
    }
    memcpy_s(Destination, 6u, (char *)a1 + 540, 6u);
  }
  v10 = *((_DWORD *)Destination + 3) + 16;
  v11.pbData = (BYTE *)Destination;
  v11.cbData = v10;
  return (unsigned int)MyCacheAddItem(a1, &v11);
}

```

## disassembly

```asm
0x18002fc8c  push    rbx
0x18002fc8e  push    rbp
0x18002fc8f  push    rsi
0x18002fc90  push    rdi
0x18002fc91  sub     rsp, 48h
0x18002fc95  mov     rbx, rcx
0x18002fc98  mov     rsi, rdx
0x18002fc9b  mov     rcx, [rcx]; struct _CARD_STATE *
0x18002fc9e  mov     rax, [rcx+8]
0x18002fca2  test    rax, rax
0x18002fca5  jnz     short loc_18002FCFE
0x18002fca7  lea     edx, [rax+2]
0x18002fcaa  lea     edi, [rax+57h]
0x18002fcad  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002fcb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fcb9  lea     rax, WPP_GLOBAL_Control
0x18002fcc0  cmp     rcx, rax
0x18002fcc3  jz      loc_18002FD75
0x18002fcc9  test    byte ptr [rcx+1Ch], 1
0x18002fccd  jz      loc_18002FD75
0x18002fcd3  cmp     byte ptr [rcx+19h], 2
0x18002fcd7  jb      loc_18002FD75
0x18002fcdd  mov     rcx, [rcx+10h]
0x18002fce1  lea     rax, aPinfoPcardstat; "pInfo->pCardState->pCardData"
0x18002fce8  lea     edx, [rdi-48h]
0x18002fceb  mov     [rsp+68h+var_48], rax
0x18002fcf0  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18002fcf7  call    WPP_SF_ss
0x18002fcfc  jmp     short loc_18002FD75
0x18002fcfe  cmp     dword ptr [rax], 6
0x18002fd01  jb      short loc_18002FD16
0x18002fd03  cmp     dword ptr [rcx+2B8h], 3
0x18002fd0a  jnz     short loc_18002FD16
0x18002fd0c  cmp     dword ptr [rbx+8], 1
0x18002fd10  jz      short loc_18002FD16
0x18002fd12  xor     eax, eax
0x18002fd14  jmp     short loc_18002FD77
0x18002fd16  cmp     dword ptr [rbx+0Ch], 0
0x18002fd1a  mov     dword ptr [rsp+68h+var_38+4], 0
0x18002fd22  jz      short loc_18002FD57
0x18002fd24  cmp     dword ptr [rbx+224h], 0
0x18002fd2b  lea     rbp, [rbx+21Ch]
0x18002fd32  jnz     short loc_18002FD42
0x18002fd34  mov     rdx, rbp; struct _CARD_CACHE_FILE_FORMAT *
0x18002fd37  call    ?I_CspReadCardCacheFile@@YAKPEAU_CARD_STATE@@PEAU_CARD_CACHE_FILE_FORMAT@@@Z; I_CspReadCardCacheFile(_CARD_STATE *,_CARD_CACHE_FILE_FORMAT *)
0x18002fd3c  mov     edi, eax
0x18002fd3e  test    eax, eax
0x18002fd40  jnz     short loc_18002FD75
0x18002fd42  mov     r9d, 6; SourceSize
0x18002fd48  mov     r8, rbp; Source
0x18002fd4b  mov     edx, r9d; DestinationSize
0x18002fd4e  mov     rcx, rsi; Destination
0x18002fd51  call    cs:__imp_memcpy_s
0x18002fd57  mov     eax, [rsi+0Ch]
0x18002fd5a  lea     rdx, [rsp+68h+var_38]; struct _CRYPTOAPI_BLOB *
0x18002fd5f  add     eax, 10h
0x18002fd62  mov     [rsp+68h+var_38.pbData], rsi
0x18002fd67  mov     rcx, rbx; struct _CARD_CACHE_QUERY_INFO *
0x18002fd6a  mov     [rsp+68h+var_38.cbData], eax
0x18002fd6e  call    ?MyCacheAddItem@@YAKPEAU_CARD_CACHE_QUERY_INFO@@PEAU_CRYPTOAPI_BLOB@@@Z; MyCacheAddItem(_CARD_CACHE_QUERY_INFO *,_CRYPTOAPI_BLOB *)
0x18002fd73  mov     edi, eax
0x18002fd75  mov     eax, edi
0x18002fd77  add     rsp, 48h
0x18002fd7b  pop     rdi
0x18002fd7c  pop     rsi
0x18002fd7d  pop     rbp
0x18002fd7e  pop     rbx
0x18002fd7f  retn
```
