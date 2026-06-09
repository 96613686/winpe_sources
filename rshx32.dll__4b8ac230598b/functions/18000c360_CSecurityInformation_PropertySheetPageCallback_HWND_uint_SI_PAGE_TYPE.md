# CSecurityInformation::PropertySheetPageCallback(HWND__ *,uint,_SI_PAGE_TYPE)

- ea: `0x18000c360`
- end: `0x18000c43e`
- name: `?PropertySheetPageCallback@CSecurityInformation@@UEAAJPEAUHWND__@@IW4_SI_PAGE_TYPE@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(CSecurityInformation *this, HWND, int, enum _SI_PAGE_TYPE)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c360`

## import_xrefs

- `ntdll!WinSqmSetDWORD` at `0x18000c41d`
- `ntdll!WinSqmSetDWORD` at `0x18000c41d`
- `ntdll!WinSqmIsOptedIn` at `0x18000c3d6`
- `ntdll!WinSqmIsOptedIn` at `0x18000c3d6`
- `USER32!GetWindowLongW` at `0x18000c39d`
- `USER32!GetWindowLongW` at `0x18000c39d`
- `USER32!GetAncestor` at `0x18000c3b1`
- `USER32!GetAncestor` at `0x18000c3b1`
- `USER32!GetWindow` at `0x18000c3be`
- `USER32!GetWindow` at `0x18000c3be`

## pseudocode

```c
__int64 __fastcall CSecurityInformation::PropertySheetPageCallback(
        CSecurityInformation *this,
        HWND a2,
        int a3,
        enum _SI_PAGE_TYPE a4)
{
  int v7; // r8d
  unsigned int v8; // ebx
  HWND Ancestor; // rax
  int v10; // eax

  v7 = a3 - 1;
  if ( v7 )
  {
    if ( v7 == 1024 )
    {
      v8 = 0;
      if ( !*((_QWORD *)this + 11) )
      {
        do
        {
          *((_QWORD *)this + 11) = a2;
          if ( (GetWindowLongW(a2, -16) & 0x40000000) != 0 )
            Ancestor = GetAncestor(a2, 1u);
          else
            Ancestor = GetWindow(a2, 4u);
          a2 = Ancestor;
        }
        while ( Ancestor );
        *((_DWORD *)this + 78) = a4;
      }
      if ( a4 == SI_PAGE_PERM && (unsigned int)WinSqmIsOptedIn() )
      {
        if ( *((_DWORD *)this + 13) == 3 )
        {
          v8 = 5;
        }
        else if ( *((_DWORD *)this + 13) == 1 )
        {
          v10 = *((_DWORD *)this + 77);
          if ( (*((_BYTE *)this + 64) & 4) != 0 )
            v8 = v10 != 0 ? 4 : 2;
          else
            v8 = v10 != 0 ? 3 : 1;
        }
        WinSqmSetDWORD(0, 9894, v8);
      }
    }
  }
  else if ( *((_DWORD *)this + 78) == a4 )
  {
    *((_QWORD *)this + 11) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c360  push    rbx
0x18000c362  push    rbp
0x18000c363  push    rsi
0x18000c364  push    rdi
0x18000c365  sub     rsp, 28h
0x18000c369  mov     ebp, r9d
0x18000c36c  mov     rsi, rdx
0x18000c36f  mov     rdi, rcx
0x18000c372  sub     r8d, 1
0x18000c376  jz      loc_18000C425
0x18000c37c  cmp     r8d, 400h
0x18000c383  jnz     loc_18000C433
0x18000c389  xor     ebx, ebx
0x18000c38b  cmp     [rcx+58h], rbx
0x18000c38f  jnz     short loc_18000C3D2
0x18000c391  mov     edx, 0FFFFFFF0h; nIndex
0x18000c396  mov     [rdi+58h], rsi
0x18000c39a  mov     rcx, rsi; hWnd
0x18000c39d  call    cs:__imp_GetWindowLongW
0x18000c3a3  mov     rcx, rsi; hWnd
0x18000c3a6  bt      eax, 1Eh
0x18000c3aa  jnb     short loc_18000C3B9
0x18000c3ac  mov     edx, 1; gaFlags
0x18000c3b1  call    cs:__imp_GetAncestor
0x18000c3b7  jmp     short loc_18000C3C4
0x18000c3b9  mov     edx, 4; uCmd
0x18000c3be  call    cs:__imp_GetWindow
0x18000c3c4  mov     rsi, rax
0x18000c3c7  test    rax, rax
0x18000c3ca  jnz     short loc_18000C391
0x18000c3cc  mov     [rdi+138h], ebp
0x18000c3d2  test    ebp, ebp
0x18000c3d4  jnz     short loc_18000C433
0x18000c3d6  call    cs:__imp_WinSqmIsOptedIn
0x18000c3dc  test    eax, eax
0x18000c3de  jz      short loc_18000C433
0x18000c3e0  cmp     dword ptr [rdi+34h], 3
0x18000c3e4  jnz     short loc_18000C3EB
0x18000c3e6  lea     ebx, [rbp+5]
0x18000c3e9  jmp     short loc_18000C413
0x18000c3eb  cmp     dword ptr [rdi+34h], 1
0x18000c3ef  jnz     short loc_18000C413
0x18000c3f1  test    byte ptr [rdi+40h], 4
0x18000c3f5  mov     eax, [rdi+134h]
0x18000c3fb  jz      short loc_18000C409
0x18000c3fd  neg     eax
0x18000c3ff  sbb     eax, eax
0x18000c401  and     eax, 2
0x18000c404  lea     ebx, [rax+2]
0x18000c407  jmp     short loc_18000C413
0x18000c409  neg     eax
0x18000c40b  sbb     eax, eax
0x18000c40d  and     eax, 2
0x18000c410  lea     ebx, [rax+1]
0x18000c413  mov     r8d, ebx
0x18000c416  mov     edx, 26A6h
0x18000c41b  xor     ecx, ecx
0x18000c41d  call    cs:__imp_WinSqmSetDWORD
0x18000c423  jmp     short loc_18000C433
0x18000c425  cmp     [rcx+138h], ebp
0x18000c42b  jnz     short loc_18000C433
0x18000c42d  xor     ebx, ebx
0x18000c42f  mov     [rcx+58h], rbx
0x18000c433  xor     eax, eax
0x18000c435  add     rsp, 28h
0x18000c439  pop     rdi
0x18000c43a  pop     rsi
0x18000c43b  pop     rbp
0x18000c43c  pop     rbx
0x18000c43d  retn
```
