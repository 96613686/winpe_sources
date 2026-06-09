# ATL::AtlModuleRegisterWndClassInfoW(ATL::_ATL_MODULE *,_ATL_WNDCLASSINFOW *,__int64 (**)(HWND__ *,uint,unsigned __int64,__int64))

- ea: `0x140002d94`
- end: `0x140002f62`
- name: `?AtlModuleRegisterWndClassInfoW@ATL@@YAGPEAU_ATL_MODULE@1@PEAU_ATL_WNDCLASSINFOW@@PEAP6A_JPEAUHWND__@@I_K_J@Z@Z`
- size: `462`
- prototype: `unsigned __int16(struct ATL::_ATL_MODULE *, struct _ATL_WNDCLASSINFOW *, __int64 (**)(HWND, unsigned int, unsigned __int64, __int64))`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400053a0`
- `0x140005450`

## callees

- `0x140001d26`
- `0x140002d94`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140002f2f`
- `KERNEL32!LeaveCriticalSection` at `0x140002f2f`
- `KERNEL32!LeaveCriticalSection` at `0x14000e4b3`
- `KERNEL32!EnterCriticalSection` at `0x140002dc5`
- `KERNEL32!EnterCriticalSection` at `0x140002dc5`
- `USER32!RegisterClassExW` at `0x140002f1e`
- `USER32!RegisterClassExW` at `0x140002f1e`
- `USER32!GetClassInfoExW` at `0x140002e15`
- `USER32!GetClassInfoExW` at `0x140002e32`
- `USER32!GetClassInfoExW` at `0x140002f0c`
- `USER32!GetClassInfoExW` at `0x140002e15`
- `USER32!GetClassInfoExW` at `0x140002e32`
- `USER32!GetClassInfoExW` at `0x140002f0c`
- `USER32!wsprintfW` at `0x140002ebe`
- `USER32!wsprintfW` at `0x140002ebe`
- `USER32!LoadCursorW` at `0x140002e91`
- `USER32!LoadCursorW` at `0x140002e91`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleRegisterWndClassInfoW(
        struct ATL::_ATL_MODULE *a1,
        struct _ATL_WNDCLASSINFOW *a2,
        __int64 (**a3)(HWND, unsigned int, unsigned __int64, __int64))
{
  int v5; // esi
  HINSTANCE v6; // rdi
  __int64 v7; // r15
  __int64 v8; // r12
  HINSTANCE v9; // rcx
  const WCHAR *v10; // rdi
  __int16 ClassInfo; // ax
  tagWNDCLASSEXW wcx; // [rsp+20h] [rbp-D8h] BYREF
  struct tagWNDCLASSEXW v14; // [rsp+70h] [rbp-88h] BYREF

  v5 = 0;
  if ( !*((_WORD *)a2 + 54) )
  {
    EnterCriticalSection(&CriticalSection);
    if ( !*((_WORD *)a2 + 54) )
    {
      v6 = hInstance;
      if ( *((_QWORD *)a2 + 10) )
      {
        v7 = *((_QWORD *)a2 + 8);
        v8 = *((_QWORD *)a2 + 1);
        memset_0(&wcx, 0, sizeof(wcx));
        wcx.cbSize = 80;
        if ( !GetClassInfoExW(0, *((LPCWSTR *)a2 + 10), &wcx)
          && !GetClassInfoExW(hInstance, *((LPCWSTR *)a2 + 10), &wcx) )
        {
          v5 = 1;
          goto LABEL_15;
        }
        *(tagWNDCLASSEXW *)a2 = wcx;
        *((_QWORD *)a2 + 11) = *((_QWORD *)a2 + 1);
        *((_QWORD *)a2 + 8) = v7;
        *((_QWORD *)a2 + 1) = v8;
      }
      else
      {
        v9 = 0;
        if ( !*((_DWORD *)a2 + 26) )
          v9 = hInstance;
        *((_QWORD *)a2 + 5) = LoadCursorW(v9, *((LPCWSTR *)a2 + 12));
      }
      *((_QWORD *)a2 + 3) = v6;
      *((_DWORD *)a2 + 1) &= ~0x4000u;
      v10 = (const WCHAR *)*((_QWORD *)a2 + 8);
      if ( !v10 )
      {
        v10 = (const WCHAR *)((char *)a2 + 110);
        wsprintfW((LPWSTR)a2 + 55, L"ATL:%p", a2);
        *((_QWORD *)a2 + 8) = (char *)a2 + 110;
      }
      v14 = *(struct tagWNDCLASSEXW *)a2;
      ClassInfo = GetClassInfoExW(*((HINSTANCE *)a2 + 3), v10, &v14);
      *((_WORD *)a2 + 54) = ClassInfo;
      if ( !ClassInfo )
        *((_WORD *)a2 + 54) = RegisterClassExW((const WNDCLASSEXW *)a2);
    }
LABEL_15:
    LeaveCriticalSection(&CriticalSection);
  }
  if ( v5 )
    return 0;
  if ( *((_QWORD *)a2 + 10) )
    *a3 = (__int64 (*)(HWND, unsigned int, unsigned __int64, __int64))*((_QWORD *)a2 + 11);
  return *((unsigned __int16 *)a2 + 54);
}

```

## disassembly

```asm
0x140002d94  push    rbx
0x140002d96  push    rsi
0x140002d97  push    rdi
0x140002d98  push    r12
0x140002d9a  push    r13
0x140002d9c  push    r14
0x140002d9e  push    r15
0x140002da0  sub     rsp, 0C0h
0x140002da7  mov     r14, r8
0x140002daa  mov     rbx, rdx
0x140002dad  xor     r13d, r13d
0x140002db0  mov     esi, r13d
0x140002db3  cmp     [rdx+6Ch], r13w
0x140002db8  jnz     loc_140002F35
0x140002dbe  lea     rcx, CriticalSection; lpCriticalSection
0x140002dc5  call    cs:__imp_EnterCriticalSection
0x140002dcb  nop
0x140002dcc  cmp     [rbx+6Ch], r13w
0x140002dd1  jnz     loc_140002F28
0x140002dd7  mov     rdi, cs:hInstance
0x140002dde  cmp     [rbx+50h], r13
0x140002de2  jz      loc_140002E82
0x140002de8  mov     r15, [rbx+40h]
0x140002dec  mov     r12, [rbx+8]
0x140002df0  mov     r13d, 50h ; 'P'
0x140002df6  mov     r8d, r13d; Size
0x140002df9  xor     edx, edx; Val
0x140002dfb  lea     rcx, [rsp+0F8h+wcx]; void *
0x140002e00  call    memset_0
0x140002e05  mov     [rsp+0F8h+wcx.cbSize], r13d
0x140002e0a  lea     r8, [rsp+0F8h+wcx]; lpwcx
0x140002e0f  mov     rdx, [rbx+50h]; lpszClass
0x140002e13  xor     ecx, ecx; hInstance
0x140002e15  call    cs:__imp_GetClassInfoExW
0x140002e1b  xor     r13d, r13d
0x140002e1e  test    eax, eax
0x140002e20  jnz     short loc_140002E44
0x140002e22  lea     r8, [rsp+0F8h+wcx]; lpwcx
0x140002e27  mov     rdx, [rbx+50h]; lpszClass
0x140002e2b  mov     rcx, cs:hInstance; hInstance
0x140002e32  call    cs:__imp_GetClassInfoExW
0x140002e38  test    eax, eax
0x140002e3a  jnz     short loc_140002E44
0x140002e3c  lea     esi, [rax+1]
0x140002e3f  jmp     loc_140002F28
0x140002e44  movaps  xmm0, xmmword ptr [rsp+0F8h+wcx.cbSize]
0x140002e49  movups  xmmword ptr [rbx], xmm0
0x140002e4c  movaps  xmm1, xmmword ptr [rsp+0F8h+wcx.cbClsExtra]
0x140002e51  movups  xmmword ptr [rbx+10h], xmm1
0x140002e55  movaps  xmm0, xmmword ptr [rsp+0F8h+wcx.hIcon]
0x140002e5a  movups  xmmword ptr [rbx+20h], xmm0
0x140002e5e  movaps  xmm1, xmmword ptr [rsp+0F8h+wcx.hbrBackground]
0x140002e63  movups  xmmword ptr [rbx+30h], xmm1
0x140002e67  movaps  xmm0, xmmword ptr [rsp+0F8h+wcx.lpszClassName]
0x140002e6c  movups  xmmword ptr [rbx+40h], xmm0
0x140002e70  mov     rax, [rbx+8]
0x140002e74  mov     [rbx+58h], rax
0x140002e78  mov     [rbx+40h], r15
0x140002e7c  mov     [rbx+8], r12
0x140002e80  jmp     short loc_140002E9B
0x140002e82  mov     rcx, r13
0x140002e85  cmp     [rbx+68h], r13d
0x140002e89  cmovz   rcx, rdi; hInstance
0x140002e8d  mov     rdx, [rbx+60h]; lpCursorName
0x140002e91  call    cs:__imp_LoadCursorW
0x140002e97  mov     [rbx+28h], rax
0x140002e9b  mov     [rbx+18h], rdi
0x140002e9f  btr     dword ptr [rbx+4], 0Eh
0x140002ea4  mov     rdi, [rbx+40h]
0x140002ea8  test    rdi, rdi
0x140002eab  jnz     short loc_140002EC8
0x140002ead  lea     rdi, [rbx+6Eh]
0x140002eb1  mov     r8, rbx
0x140002eb4  lea     rdx, aAtlP; "ATL:%p"
0x140002ebb  mov     rcx, rdi; LPWSTR
0x140002ebe  call    cs:__imp_wsprintfW
0x140002ec4  mov     [rbx+40h], rdi
0x140002ec8  movups  xmm0, xmmword ptr [rbx]
0x140002ecb  movaps  xmmword ptr [rsp+0F8h+var_88.cbSize], xmm0
0x140002ed0  movups  xmm1, xmmword ptr [rbx+10h]
0x140002ed4  movaps  xmmword ptr [rsp+0F8h+var_88.cbClsExtra], xmm1
0x140002edc  movups  xmm0, xmmword ptr [rbx+20h]
0x140002ee0  movaps  xmmword ptr [rsp+0F8h+var_88.hIcon], xmm0
0x140002ee8  movups  xmm1, xmmword ptr [rbx+30h]
0x140002eec  movaps  xmmword ptr [rsp+0F8h+var_88.hbrBackground], xmm1
0x140002ef4  movups  xmm0, xmmword ptr [rbx+40h]
0x140002ef8  movaps  xmmword ptr [rsp+0F8h+var_88.lpszClassName], xmm0
0x140002f00  lea     r8, [rsp+0F8h+var_88]; lpwcx
0x140002f05  mov     rdx, rdi; lpszClass
0x140002f08  mov     rcx, [rbx+18h]; hInstance
0x140002f0c  call    cs:__imp_GetClassInfoExW
0x140002f12  mov     [rbx+6Ch], ax
0x140002f16  test    ax, ax
0x140002f19  jnz     short loc_140002F28
0x140002f1b  mov     rcx, rbx; WNDCLASSEXW *
0x140002f1e  call    cs:__imp_RegisterClassExW
0x140002f24  mov     [rbx+6Ch], ax
0x140002f28  lea     rcx, CriticalSection; lpCriticalSection
0x140002f2f  call    cs:__imp_LeaveCriticalSection
0x140002f35  test    esi, esi
0x140002f37  jz      short loc_140002F3E
0x140002f39  mov     eax, r13d
0x140002f3c  jmp     short loc_140002F4F
0x140002f3e  cmp     [rbx+50h], r13
0x140002f42  jz      short loc_140002F4B
0x140002f44  mov     rax, [rbx+58h]
0x140002f48  mov     [r14], rax
0x140002f4b  movzx   eax, word ptr [rbx+6Ch]
0x140002f4f  add     rsp, 0C0h
0x140002f56  pop     r15
0x140002f58  pop     r14
0x140002f5a  pop     r13
0x140002f5c  pop     r12
0x140002f5e  pop     rdi
0x140002f5f  pop     rsi
0x140002f60  pop     rbx
0x140002f61  retn
0x14000e49e  push    rbp
0x14000e4a0  sub     rsp, 20h
0x14000e4a4  mov     rbp, rdx
0x14000e4a7  lea     rcx, CriticalSection
0x14000e4ae  add     rsp, 20h
0x14000e4b2  pop     rbp
0x14000e4b3  jmp     cs:__imp_LeaveCriticalSection
```
