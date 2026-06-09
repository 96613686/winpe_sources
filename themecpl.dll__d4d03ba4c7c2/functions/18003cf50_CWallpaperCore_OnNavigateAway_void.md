# CWallpaperCore::OnNavigateAway(void)

- ea: `0x18003cf50`
- end: `0x18003d08e`
- name: `?OnNavigateAway@CWallpaperCore@@QEAAXXZ`
- size: `318`
- prototype: `void __fastcall(CWallpaperCore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180044850`

## callees

- `0x18003cf50`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d051`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d051`
- `USER32!DestroyWindow` at `0x18003d002`
- `USER32!DestroyWindow` at `0x18003d002`

## pseudocode

```c
void __fastcall CWallpaperCore::OnNavigateAway(CWallpaperCore *this)
{
  int (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  HWND v3; // rcx
  __int64 v4; // rcx
  __int64 i; // rsi
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_BYTE *)this + 74) )
  {
    if ( *((_QWORD *)this + 53) )
    {
      v2 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 52);
      v6 = 0;
      if ( (**v2)(v2, &GUID_00000109_0000_0000_c000_000000000046, &v6) >= 0 )
      {
        if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 53) + 40LL))(
               *((_QWORD *)this + 53),
               0,
               0,
               0) >= 0 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 40LL))(v6, *((_QWORD *)this + 53));
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
    }
  }
  if ( *((_QWORD *)this + 21) )
    *((_QWORD *)this + 21) = 0;
  v3 = (HWND)*((_QWORD *)this + 7);
  if ( v3 )
  {
    DestroyWindow(v3);
    *((_QWORD *)this + 7) = 0;
  }
  v4 = *((_QWORD *)this + 53);
  *((_WORD *)this + 37) = 256;
  *((_QWORD *)this + 53) = 0;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 55); i = (unsigned int)(i + 1) )
  {
    CoTaskMemFree(*((LPVOID *)this + i + 28));
    *((_QWORD *)this + i + 28) = 0;
  }
  *((_DWORD *)this + 55) = 0;
}

```

## disassembly

```asm
0x18003cf50  mov     r11, rsp
0x18003cf53  mov     [r11+10h], rbx
0x18003cf57  mov     [r11+18h], rsi
0x18003cf5b  push    rdi
0x18003cf5c  sub     rsp, 30h
0x18003cf60  cmp     byte ptr [rcx+4Ah], 0
0x18003cf64  mov     rdi, rcx
0x18003cf67  jz      short loc_18003CFE4
0x18003cf69  cmp     qword ptr [rcx+1A8h], 0
0x18003cf71  jz      short loc_18003CFE4
0x18003cf73  mov     rcx, [rcx+1A0h]
0x18003cf7a  lea     r8, [r11+8]
0x18003cf7e  mov     qword ptr [r11+8], 0
0x18003cf86  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18003cf8d  mov     rax, [rcx]
0x18003cf90  mov     rax, [rax]
0x18003cf93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf98  test    eax, eax
0x18003cf9a  js      short loc_18003CFE4
0x18003cf9c  mov     rcx, [rdi+1A8h]
0x18003cfa3  xor     edx, edx
0x18003cfa5  xor     r9d, r9d
0x18003cfa8  xor     r8d, r8d
0x18003cfab  mov     rax, [rcx]
0x18003cfae  mov     rax, [rax+28h]
0x18003cfb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfb7  test    eax, eax
0x18003cfb9  js      short loc_18003CFD3
0x18003cfbb  mov     rcx, [rsp+38h+arg_0]
0x18003cfc0  mov     rdx, [rdi+1A8h]
0x18003cfc7  mov     rax, [rcx]
0x18003cfca  mov     rax, [rax+28h]
0x18003cfce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfd3  mov     rcx, [rsp+38h+arg_0]
0x18003cfd8  mov     rax, [rcx]
0x18003cfdb  mov     rax, [rax+10h]
0x18003cfdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfe4  cmp     qword ptr [rdi+0A8h], 0
0x18003cfec  jz      short loc_18003CFF9
0x18003cfee  mov     qword ptr [rdi+0A8h], 0
0x18003cff9  mov     rcx, [rdi+38h]; hWnd
0x18003cffd  test    rcx, rcx
0x18003d000  jz      short loc_18003D016
0x18003d002  call    cs:__imp_DestroyWindow
0x18003d009  nop     dword ptr [rax+rax+00h]
0x18003d00e  mov     qword ptr [rdi+38h], 0
0x18003d016  mov     rcx, [rdi+1A8h]
0x18003d01d  mov     word ptr [rdi+4Ah], 100h
0x18003d023  mov     qword ptr [rdi+1A8h], 0
0x18003d02e  test    rcx, rcx
0x18003d031  jz      short loc_18003D03F
0x18003d033  mov     rax, [rcx]
0x18003d036  mov     rax, [rax+10h]
0x18003d03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d03f  xor     esi, esi
0x18003d041  cmp     [rdi+0DCh], esi
0x18003d047  jbe     short loc_18003D073
0x18003d049  mov     rcx, [rdi+rsi*8+0E0h]; pv
0x18003d051  call    cs:__imp_CoTaskMemFree
0x18003d058  nop     dword ptr [rax+rax+00h]
0x18003d05d  mov     qword ptr [rdi+rsi*8+0E0h], 0
0x18003d069  inc     esi
0x18003d06b  cmp     esi, [rdi+0DCh]
0x18003d071  jb      short loc_18003D049
0x18003d073  mov     rbx, [rsp+38h+arg_8]
0x18003d078  mov     rsi, [rsp+38h+arg_10]
0x18003d07d  mov     dword ptr [rdi+0DCh], 0
0x18003d087  add     rsp, 30h
0x18003d08b  pop     rdi
0x18003d08c  retn
```
