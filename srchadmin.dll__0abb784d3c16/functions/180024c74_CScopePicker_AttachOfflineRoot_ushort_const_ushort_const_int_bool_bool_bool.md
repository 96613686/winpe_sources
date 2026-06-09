# CScopePicker::_AttachOfflineRoot(ushort const *,ushort const *,int,bool,bool,bool)

- ea: `0x180024c74`
- end: `0x180024de1`
- name: `?_AttachOfflineRoot@CScopePicker@@AEAAJPEBG0H_N11@Z`
- size: `365`
- prototype: `__int64 __fastcall(CScopePicker *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int, bool, bool, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180024260`
- `0x180024360`
- `0x180025270`

## callees

- `0x180005cc0`
- `0x18000687c`
- `0x18000957c`
- `0x18001a7fc`
- `0x180024c74`
- `0x180026b10`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180024cc1`
- `SHLWAPI!SHStrDupW` at `0x180024cc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024dbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024dbe`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180024d88`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180024d88`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CScopePicker::_AttachOfflineRoot(
        CScopePicker *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        bool a5,
        bool a6,
        bool a7)
{
  LPCWSTR v9; // r11
  HRESULT v10; // ebx
  _QWORD *v11; // rax
  _QWORD *v12; // rbx
  HWND v13; // rcx
  LRESULT v14; // rax
  LPWSTR ppwsz; // [rsp+20h] [rbp-E0h] BYREF
  LPARAM lParam[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+64h] [rbp-9Ch]
  int v21; // [rsp+68h] [rbp-98h]
  _QWORD *v22; // [rsp+70h] [rbp-90h]
  unsigned __int16 v23[264]; // [rsp+90h] [rbp-70h] BYREF

  StringCchCopyW(v23, 0x104u, a3);
  ppwsz = 0;
  v10 = SHStrDupW(v9, &ppwsz);
  if ( v10 < 0 )
    goto LABEL_7;
  v11 = operator new(0x30u);
  v12 = v11;
  if ( !v11 )
  {
    v10 = -2147024882;
    goto LABEL_7;
  }
  *v11 = 0;
  v11[1] = 0;
  v11[2] = 0;
  *((_DWORD *)v11 + 6) = 0;
  *(_QWORD *)((char *)v11 + 28) = 1;
  *((_DWORD *)v11 + 9) = 0;
  *((_BYTE *)v11 + 44) = 0;
  v11[1] = ppwsz;
  *((_DWORD *)v11 + 7) = 0;
  *((_DWORD *)v11 + 8) = a7;
  *((_BYTE *)v11 + 44) = a6;
  memset_0(lParam, 0, 0x60u);
  v13 = (HWND)*((_QWORD *)this + 3);
  *(__m128i *)lParam = _mm_load_si128((const __m128i *)&_xmm_ffffffffffff0002ffffffffffff0000);
  v19 = v23;
  v18 = 39;
  v22 = v12;
  v20 = a4;
  v21 = a4;
  v14 = SendMessageW(v13, 0x1132u, 0, (LPARAM)lParam);
  if ( !v14 )
  {
    v10 = -2147467259;
LABEL_7:
    CoTaskMemFree(ppwsz);
    return (unsigned int)v10;
  }
  v10 = 0;
  CScopePicker::_UpdateStateIcon(this, v14, (unsigned int)a5 + 1);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180024c74  push    rbp
0x180024c76  push    rbx
0x180024c77  push    rsi
0x180024c78  push    rdi
0x180024c79  lea     rbp, [rsp-1B8h]
0x180024c81  sub     rsp, 2B8h
0x180024c88  mov     rax, cs:__security_cookie
0x180024c8f  xor     rax, rsp
0x180024c92  mov     [rbp+1D0h+var_30], rax
0x180024c99  mov     r11, rdx
0x180024c9c  mov     rdi, rcx
0x180024c9f  mov     edx, 104h; unsigned __int64
0x180024ca4  lea     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x180024ca8  mov     esi, r9d
0x180024cab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024cb0  lea     rdx, [rsp+2D0h+ppwsz]; ppwsz
0x180024cb5  mov     [rsp+2D0h+ppwsz], 0
0x180024cbe  mov     rcx, r11; psz
0x180024cc1  call    cs:__imp_SHStrDupW
0x180024cc7  mov     ebx, eax
0x180024cc9  test    eax, eax
0x180024ccb  js      loc_180024DB9
0x180024cd1  mov     ecx, 30h ; '0'; unsigned __int64
0x180024cd6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024cdb  mov     rbx, rax
0x180024cde  test    rax, rax
0x180024ce1  jz      loc_180024DB4
0x180024ce7  mov     qword ptr [rax], 0
0x180024cee  xor     edx, edx; Val
0x180024cf0  mov     qword ptr [rax+8], 0
0x180024cf8  mov     qword ptr [rax+10h], 0
0x180024d00  mov     dword ptr [rax+18h], 0
0x180024d07  mov     qword ptr [rax+1Ch], 1
0x180024d0f  lea     r8d, [rdx+60h]; Size
0x180024d13  mov     dword ptr [rax+24h], 0
0x180024d1a  mov     byte ptr [rax+2Ch], 0
0x180024d1e  mov     rcx, [rsp+2D0h+ppwsz]
0x180024d23  mov     [rax+8], rcx
0x180024d27  lea     rcx, [rsp+2D0h+lParam]; void *
0x180024d2c  mov     dword ptr [rax+1Ch], 0
0x180024d33  movzx   eax, [rbp+1D0h+arg_30]
0x180024d3a  mov     [rbx+20h], eax
0x180024d3d  mov     al, [rbp+1D0h+arg_28]
0x180024d43  mov     [rbx+2Ch], al
0x180024d46  call    memset_0
0x180024d4b  movdqa  xmm0, cs:__xmm@ffffffffffff0002ffffffffffff0000
0x180024d53  lea     rax, [rbp+1D0h+var_240]
0x180024d57  mov     rcx, [rdi+18h]; hWnd
0x180024d5b  lea     r9, [rsp+2D0h+lParam]; lParam
0x180024d60  xor     r8d, r8d; wParam
0x180024d63  movdqa  xmmword ptr [rsp+2D0h+lParam], xmm0
0x180024d69  mov     edx, 1132h; Msg
0x180024d6e  mov     [rsp+2D0h+var_278], rax
0x180024d73  mov     [rsp+2D0h+var_290], 27h ; '''
0x180024d7b  mov     [rsp+2D0h+var_260], rbx
0x180024d80  mov     [rsp+2D0h+var_26C], esi
0x180024d84  mov     [rsp+2D0h+var_268], esi
0x180024d88  call    cs:__imp_SendMessageW
0x180024d8e  test    rax, rax
0x180024d91  jz      short loc_180024DAD
0x180024d93  movzx   r8d, [rbp+1D0h+arg_20]
0x180024d9b  xor     ebx, ebx
0x180024d9d  inc     r8d
0x180024da0  mov     rdx, rax
0x180024da3  mov     rcx, rdi
0x180024da6  call    ?_UpdateStateIcon@CScopePicker@@AEAAXPEAU_TREEITEM@@W4_TREE_ITEM_CHECK@@@Z; CScopePicker::_UpdateStateIcon(_TREEITEM *,_TREE_ITEM_CHECK)
0x180024dab  jmp     short loc_180024DC4
0x180024dad  mov     ebx, 80004005h
0x180024db2  jmp     short loc_180024DB9
0x180024db4  mov     ebx, 8007000Eh
0x180024db9  mov     rcx, [rsp+2D0h+ppwsz]; pv
0x180024dbe  call    cs:__imp_CoTaskMemFree
0x180024dc4  mov     eax, ebx
0x180024dc6  mov     rcx, [rbp+1D0h+var_30]
0x180024dcd  xor     rcx, rsp; StackCookie
0x180024dd0  call    __security_check_cookie
0x180024dd5  add     rsp, 2B8h
0x180024ddc  pop     rdi
0x180024ddd  pop     rsi
0x180024dde  pop     rbx
0x180024ddf  pop     rbp
0x180024de0  retn
```
