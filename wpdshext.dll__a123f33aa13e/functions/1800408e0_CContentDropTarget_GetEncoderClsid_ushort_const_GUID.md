# CContentDropTarget::_GetEncoderClsid(ushort const *,_GUID *)

- ea: `0x1800408e0`
- end: `0x1800409a5`
- name: `?_GetEncoderClsid@CContentDropTarget@@AEAAHPEBGPEAU_GUID@@@Z`
- size: `197`
- prototype: `int(CContentDropTarget *__hidden this, const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004123c`

## callees

- `0x1800408e0`

## import_xrefs

- `SHLWAPI!StrCmpW` at `0x18004096f`
- `SHLWAPI!StrCmpW` at `0x18004096f`
- `gdiplus!GdipGetImageEncoders` at `0x18004094c`
- `gdiplus!GdipGetImageEncoders` at `0x18004094c`
- `gdiplus!GdipGetImageEncodersSize` at `0x180040923`
- `gdiplus!GdipGetImageEncodersSize` at `0x180040923`
- `ole32!CoTaskMemFree` at `0x18004098c`
- `ole32!CoTaskMemFree` at `0x18004098c`
- `ole32!CoTaskMemAlloc` at `0x180040933`
- `ole32!CoTaskMemAlloc` at `0x180040933`

## pseudocode

```c
__int64 __fastcall CContentDropTarget::_GetEncoderClsid(
        CContentDropTarget *this,
        const unsigned __int16 *a2,
        struct _GUID *a3)
{
  unsigned int v5; // ebx
  char *v6; // rax
  char *v7; // rsi
  unsigned int i; // edi
  __int64 v9; // r15
  unsigned int cb; // [rsp+50h] [rbp+8h] BYREF
  int cb_4; // [rsp+54h] [rbp+Ch]
  unsigned int v13; // [rsp+58h] [rbp+10h] BYREF

  cb_4 = HIDWORD(this);
  v13 = 0;
  cb = 0;
  if ( a2 && a3 && (GdipGetImageEncodersSize(&v13, &cb), cb) && (v6 = (char *)CoTaskMemAlloc(cb), (v7 = v6) != 0) )
  {
    v5 = -1;
    if ( !(unsigned int)GdipGetImageEncoders(v13, cb, v6) )
    {
      for ( i = 0; i < v13; ++i )
      {
        v9 = 104LL * i;
        if ( !StrCmpW(*(PCWSTR *)&v7[v9 + 64], a2) )
        {
          v5 = i;
          *a3 = *(struct _GUID *)&v7[v9];
          break;
        }
      }
    }
    CoTaskMemFree(v7);
  }
  else
  {
    return (unsigned int)-1;
  }
  return v5;
}

```

## disassembly

```asm
0x1800408e0  mov     rax, rsp
0x1800408e3  mov     [rax+18h], rbx
0x1800408e7  mov     [rax+8], rcx
0x1800408eb  push    rbp
0x1800408ec  push    rsi
0x1800408ed  push    rdi
0x1800408ee  push    r14
0x1800408f0  push    r15
0x1800408f2  sub     rsp, 20h
0x1800408f6  mov     dword ptr [rax+10h], 0
0x1800408fd  mov     rbp, r8
0x180040900  mov     dword ptr [rax+8], 0
0x180040907  mov     r14, rdx
0x18004090a  test    rdx, rdx
0x18004090d  jnz     short loc_180040914
0x18004090f  or      ebx, 0FFFFFFFFh
0x180040912  jmp     short loc_180040992
0x180040914  test    rbp, rbp
0x180040917  jz      short loc_18004090F
0x180040919  lea     rdx, [rsp+48h+cb]
0x18004091e  lea     rcx, [rsp+48h+arg_8]
0x180040923  call    cs:__imp_GdipGetImageEncodersSize
0x180040929  mov     eax, dword ptr [rsp+48h+cb]
0x18004092d  test    eax, eax
0x18004092f  jz      short loc_18004090F
0x180040931  mov     ecx, eax; cb
0x180040933  call    cs:__imp_CoTaskMemAlloc
0x180040939  mov     rsi, rax
0x18004093c  test    rax, rax
0x18004093f  jz      short loc_18004090F
0x180040941  mov     edx, dword ptr [rsp+48h+cb]
0x180040945  mov     r8, rax
0x180040948  mov     ecx, [rsp+48h+arg_8]
0x18004094c  call    cs:__imp_GdipGetImageEncoders
0x180040952  or      ebx, 0FFFFFFFFh
0x180040955  test    eax, eax
0x180040957  jnz     short loc_180040989
0x180040959  xor     edi, edi
0x18004095b  cmp     edi, [rsp+48h+arg_8]
0x18004095f  jnb     short loc_180040989
0x180040961  mov     eax, edi
0x180040963  mov     rdx, r14; psz2
0x180040966  imul    r15, rax, 68h ; 'h'
0x18004096a  mov     rcx, [r15+rsi+40h]; psz1
0x18004096f  call    cs:__imp_StrCmpW
0x180040975  test    eax, eax
0x180040977  jz      short loc_18004097D
0x180040979  inc     edi
0x18004097b  jmp     short loc_18004095B
0x18004097d  movups  xmm0, xmmword ptr [r15+rsi]
0x180040982  mov     ebx, edi
0x180040984  movdqu  xmmword ptr [rbp+0], xmm0
0x180040989  mov     rcx, rsi; pv
0x18004098c  call    cs:__imp_CoTaskMemFree
0x180040992  mov     eax, ebx
0x180040994  mov     rbx, [rsp+48h+arg_10]
0x180040999  add     rsp, 20h
0x18004099d  pop     r15
0x18004099f  pop     r14
0x1800409a1  pop     rdi
0x1800409a2  pop     rsi
0x1800409a3  pop     rbp
0x1800409a4  retn
```
