# CNTFSSecurity::GetSecondarySecurity(_SECURITY_OBJECT * *,ulong *)

- ea: `0x1800070b0`
- end: `0x18000724a`
- name: `?GetSecondarySecurity@CNTFSSecurity@@UEAAJPEAPEAU_SECURITY_OBJECT@@PEAK@Z`
- size: `410`
- prototype: `__int64 __fastcall(CNTFSSecurity *__hidden this, struct _SECURITY_OBJECT **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005610`
- `0x1800070b0`
- `0x18000b6b4`
- `0x18001d33a`
- `0x18001d370`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180007182`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180007182`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800071b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800071b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007149`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000719a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007149`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000719a`

## pseudocode

```c
__int64 __fastcall CNTFSSecurity::GetSecondarySecurity(
        CNTFSSecurity *this,
        struct _SECURITY_OBJECT **a2,
        unsigned int *a3)
{
  int *v6; // r9
  int v7; // r8d
  unsigned __int16 *v8; // rdx
  unsigned __int16 *v9; // rcx
  _BOOL8 v10; // r15
  _QWORD *v11; // rsi
  unsigned int v12; // ebx
  int StringW; // eax
  unsigned __int64 v14; // rbx
  unsigned __int16 *v15; // rax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-248h] BYREF

  memset_0(Buffer, 0, 0x208u);
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  if ( !*((_BYTE *)this + 368) )
  {
    v7 = *((_DWORD *)this + 67);
    v8 = (unsigned __int16 *)*((_QWORD *)this + 2);
    v9 = (unsigned __int16 *)*((_QWORD *)this + 4);
    *((_BYTE *)this + 368) = 1;
    *((_QWORD *)this + 45) = CShareSecurityInformation::InitializeShare(v9, v8, v7, v6);
  }
  v10 = *((_QWORD *)this + 45) != 0;
  v11 = LocalAlloc(0x40u, 48 * v10);
  if ( v11 )
  {
    if ( !*((_QWORD *)this + 42) )
    {
      StringW = LoadStringW(g_hInstance, 0x58u, Buffer, 260);
      if ( StringW <= 0
        || (v14 = StringW + 1, v15 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v14), (*((_QWORD *)this + 42) = v15) == 0) )
      {
        v12 = -2147024882;
        LocalFree(v11);
        return v12;
      }
      StringCchCopyW(v15, v14, Buffer);
    }
    v12 = 0;
    if ( *((_QWORD *)this + 45) )
    {
      *((_BYTE *)v11 + 40) = 1;
      *((_DWORD *)v11 + 9) = 2;
      *((_DWORD *)v11 + 4) = 272;
      v11[1] = *((_QWORD *)this + 45);
      *v11 = *((_QWORD *)this + 42);
      v11[3] = *(_QWORD *)(*((_QWORD *)this + 45) + 232LL);
      *((_DWORD *)v11 + 8) = 0;
    }
    *a2 = (struct _SECURITY_OBJECT *)v11;
    *a3 = v10;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v12;
}

```

## disassembly

```asm
0x1800070b0  mov     [rsp+arg_18], rbx
0x1800070b5  push    rbp
0x1800070b6  push    rsi
0x1800070b7  push    rdi
0x1800070b8  push    r14
0x1800070ba  push    r15
0x1800070bc  sub     rsp, 240h
0x1800070c3  mov     rax, cs:__security_cookie
0x1800070ca  xor     rax, rsp
0x1800070cd  mov     [rsp+268h+var_38], rax
0x1800070d5  mov     r14, r8
0x1800070d8  mov     rbp, rdx
0x1800070db  mov     rdi, rcx
0x1800070de  xor     edx, edx; Val
0x1800070e0  mov     r8d, 208h; Size
0x1800070e6  lea     rcx, [rsp+268h+Buffer]; void *
0x1800070eb  call    memset_0
0x1800070f0  test    rbp, rbp
0x1800070f3  jz      loc_18000721C
0x1800070f9  test    r14, r14
0x1800070fc  jz      loc_18000721C
0x180007102  cmp     byte ptr [rdi+170h], 0
0x180007109  jnz     short loc_18000712D
0x18000710b  mov     r8d, [rdi+10Ch]; int
0x180007112  mov     rdx, [rdi+10h]; unsigned __int16 *
0x180007116  mov     rcx, [rdi+20h]; unsigned __int16 *
0x18000711a  mov     byte ptr [rdi+170h], 1
0x180007121  call    ?InitializeShare@CShareSecurityInformation@@SAPEAV1@PEAG0HPEAJ@Z; CShareSecurityInformation::InitializeShare(ushort *,ushort *,int,long *)
0x180007126  mov     [rdi+168h], rax
0x18000712d  xor     eax, eax
0x18000712f  mov     ecx, 40h ; '@'; uFlags
0x180007134  cmp     [rdi+168h], rax
0x18000713b  setnz   al
0x18000713e  mov     r15d, eax
0x180007141  lea     rdx, [r15+r15*2]
0x180007145  shl     rdx, 4; uBytes
0x180007149  call    cs:__imp_LocalAlloc
0x18000714f  mov     rsi, rax
0x180007152  test    rax, rax
0x180007155  jnz     short loc_180007161
0x180007157  mov     ebx, 8007000Eh
0x18000715c  jmp     loc_180007221
0x180007161  cmp     qword ptr [rdi+150h], 0
0x180007169  jnz     short loc_1800071CC
0x18000716b  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180007172  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x180007177  mov     r9d, 104h; cchBufferMax
0x18000717d  mov     edx, 58h ; 'X'; uID
0x180007182  call    cs:__imp_LoadStringW
0x180007188  test    eax, eax
0x18000718a  jle     short loc_1800071AC
0x18000718c  inc     eax
0x18000718e  mov     ecx, 40h ; '@'; uFlags
0x180007193  movsxd  rbx, eax
0x180007196  lea     rdx, [rbx+rbx]; uBytes
0x18000719a  call    cs:__imp_LocalAlloc
0x1800071a0  mov     [rdi+150h], rax
0x1800071a7  test    rax, rax
0x1800071aa  jnz     short loc_1800071BC
0x1800071ac  mov     rcx, rsi; hMem
0x1800071af  mov     ebx, 8007000Eh
0x1800071b4  call    cs:__imp_LocalFree
0x1800071ba  jmp     short loc_180007221
0x1800071bc  lea     r8, [rsp+268h+Buffer]; unsigned __int16 *
0x1800071c1  mov     rdx, rbx; unsigned __int64
0x1800071c4  mov     rcx, rax; unsigned __int16 *
0x1800071c7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800071cc  xor     ebx, ebx
0x1800071ce  cmp     [rdi+168h], rbx
0x1800071d5  jz      short loc_180007213
0x1800071d7  mov     byte ptr [rsi+28h], 1
0x1800071db  mov     dword ptr [rsi+24h], 2
0x1800071e2  mov     dword ptr [rsi+10h], 110h
0x1800071e9  mov     rax, [rdi+168h]
0x1800071f0  mov     [rsi+8], rax
0x1800071f4  mov     rax, [rdi+150h]
0x1800071fb  mov     [rsi], rax
0x1800071fe  mov     rax, [rdi+168h]
0x180007205  mov     rcx, [rax+0E8h]
0x18000720c  mov     [rsi+18h], rcx
0x180007210  mov     [rsi+20h], ebx
0x180007213  mov     [rbp+0], rsi
0x180007217  mov     [r14], r15d
0x18000721a  jmp     short loc_180007221
0x18000721c  mov     ebx, 80070057h
0x180007221  mov     eax, ebx
0x180007223  mov     rcx, [rsp+268h+var_38]
0x18000722b  xor     rcx, rsp; StackCookie
0x18000722e  call    __security_check_cookie
0x180007233  mov     rbx, [rsp+268h+arg_18]
0x18000723b  add     rsp, 240h
0x180007242  pop     r15
0x180007244  pop     r14
0x180007246  pop     rdi
0x180007247  pop     rsi
0x180007248  pop     rbp
0x180007249  retn
```
