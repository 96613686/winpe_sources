# GetFinalPathNameByHandleW

- ea: `0x140019a5c`
- end: `0x140019f62`
- name: `GetFinalPathNameByHandleW`
- size: `1286`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, loader_planting`

## callers

- `0x14001598c`
- `0x14001b450`

## callees

- `0x140019154`
- `0x140019244`
- `0x14001933c`
- `0x140019678`
- `0x140019a5c`
- `0x140019f68`
- `0x140019ff4`
- `0x14001ae48`
- `0x14001cc1d`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140019d5a`
- `ntdll!RtlAllocateHeap` at `0x140019d5a`
- `ntdll!RtlFreeHeap` at `0x140019b57`
- `ntdll!RtlFreeHeap` at `0x140019b74`
- `ntdll!RtlFreeHeap` at `0x140019b91`
- `ntdll!RtlFreeHeap` at `0x140019d7f`
- `ntdll!RtlFreeHeap` at `0x140019de4`
- `ntdll!RtlFreeHeap` at `0x140019e05`
- `ntdll!RtlFreeHeap` at `0x140019e4b`
- `ntdll!RtlFreeHeap` at `0x140019e67`
- `ntdll!RtlFreeHeap` at `0x140019ec4`
- `ntdll!RtlFreeHeap` at `0x140019edc`
- `ntdll!RtlFreeHeap` at `0x140019ef9`
- `ntdll!RtlFreeHeap` at `0x140019b57`
- `ntdll!RtlFreeHeap` at `0x140019b74`
- `ntdll!RtlFreeHeap` at `0x140019b91`
- `ntdll!RtlFreeHeap` at `0x140019d7f`
- `ntdll!RtlFreeHeap` at `0x140019de4`
- `ntdll!RtlFreeHeap` at `0x140019e05`
- `ntdll!RtlFreeHeap` at `0x140019e4b`
- `ntdll!RtlFreeHeap` at `0x140019e67`
- `ntdll!RtlFreeHeap` at `0x140019ec4`
- `ntdll!RtlFreeHeap` at `0x140019edc`
- `ntdll!RtlFreeHeap` at `0x140019ef9`
- `ntdll!wcslen` at `0x140019bb2`
- `ntdll!wcslen` at `0x140019bbe`
- `ntdll!wcslen` at `0x140019bdc`
- `ntdll!wcslen` at `0x140019be8`
- `ntdll!wcslen` at `0x140019d1f`
- `ntdll!wcslen` at `0x140019d2b`
- `ntdll!wcslen` at `0x140019e1d`
- `ntdll!wcslen` at `0x140019e2d`
- `ntdll!wcslen` at `0x140019e7f`
- `ntdll!wcslen` at `0x140019e8a`
- `ntdll!wcslen` at `0x140019f0b`
- `ntdll!wcslen` at `0x140019f17`
- `ntdll!wcslen` at `0x140019bb2`
- `ntdll!wcslen` at `0x140019bbe`
- `ntdll!wcslen` at `0x140019bdc`
- `ntdll!wcslen` at `0x140019be8`
- `ntdll!wcslen` at `0x140019d1f`
- `ntdll!wcslen` at `0x140019d2b`
- `ntdll!wcslen` at `0x140019e1d`
- `ntdll!wcslen` at `0x140019e2d`
- `ntdll!wcslen` at `0x140019e7f`
- `ntdll!wcslen` at `0x140019e8a`
- `ntdll!wcslen` at `0x140019f0b`
- `ntdll!wcslen` at `0x140019f17`
- `ntdll!RtlSetLastWin32Error` at `0x140019aa3`
- `ntdll!RtlSetLastWin32Error` at `0x140019b36`
- `ntdll!RtlSetLastWin32Error` at `0x140019bce`
- `ntdll!RtlSetLastWin32Error` at `0x140019c4f`
- `ntdll!RtlSetLastWin32Error` at `0x140019aa3`
- `ntdll!RtlSetLastWin32Error` at `0x140019b36`
- `ntdll!RtlSetLastWin32Error` at `0x140019bce`
- `ntdll!RtlSetLastWin32Error` at `0x140019c4f`

## pseudocode

```c
__int64 __fastcall GetFinalPathNameByHandleW(HANDLE Handle, wchar_t *a2, unsigned int a3, char a4)
{
  unsigned int v5; // r13d
  wchar_t *v6; // rsi
  wchar_t *v7; // r15
  ULONG v8; // ecx
  int v9; // r8d
  int v10; // edi
  unsigned __int16 v11; // cx
  unsigned __int16 v12; // dx
  const wchar_t *v14; // r14
  size_t v15; // rbx
  ULONG v16; // ecx
  size_t v17; // rbx
  int v18; // ebx
  wchar_t *v19; // rdi
  const wchar_t *v20; // rcx
  int v21; // ebx
  wchar_t *Heap; // rax
  wchar_t *v23; // r12
  const wchar_t *v24; // r8
  size_t v25; // rbx
  unsigned int LongPathNameW; // ebx
  int v27; // ebx
  int v28; // eax
  const wchar_t *v29; // rcx
  __int64 v30; // rbx
  size_t v31; // rax
  int v32; // eax
  size_t v33; // r11
  STRSAFE_LPCWSTR pszSrc; // [rsp+20h] [rbp-28h] BYREF
  PVOID BaseAddress; // [rsp+28h] [rbp-20h] BYREF
  wchar_t *Str; // [rsp+30h] [rbp-18h]
  int v37; // [rsp+90h] [rbp+48h]
  unsigned int v38; // [rsp+90h] [rbp+48h]
  unsigned int v39; // [rsp+90h] [rbp+48h]

  pszSrc = 0;
  Str = 0;
  v5 = 0;
  BaseAddress = 0;
  v6 = 0;
  v7 = 0;
  if ( Handle == (HANDLE)-1LL )
  {
    v8 = 6;
LABEL_3:
    RtlSetLastWin32Error(v8);
    return v5;
  }
  v9 = a4 & 1;
  v10 = 0;
  if ( (a4 & 2) != 0 )
    v9 = 2;
  v11 = (a4 & 1) + 1;
  if ( (a4 & 2) == 0 )
    v11 = a4 & 1;
  if ( (a4 & 4) == 0 )
    v10 = v9;
  v12 = v11 + 1;
  if ( (a4 & 4) == 0 )
    v12 = v11;
  if ( v12 > 1u )
  {
    v8 = 87;
    goto LABEL_3;
  }
  if ( !v12 )
    v10 = 3;
  v37 = v10;
  if ( (unsigned int)BasepGetObjectNTName(Handle) )
  {
    v7 = Str;
    if ( (unsigned int)BasepGetFileNameInformation(Handle, FileNameInformation) )
    {
      if ( *Str != 92 )
      {
        RtlSetLastWin32Error(5u);
        goto LABEL_20;
      }
      v14 = (const wchar_t *)BaseAddress;
      v15 = wcslen((const wchar_t *)BaseAddress);
      if ( wcslen(Str) >= v15 )
      {
        v16 = 161;
LABEL_27:
        RtlSetLastWin32Error(v16);
        goto LABEL_20;
      }
      v17 = wcslen((const wchar_t *)BaseAddress);
      *((_WORD *)BaseAddress + v17 - wcslen(Str)) = 0;
      if ( v10 != 1 )
      {
        if ( v10 == 2 )
        {
          v18 = 0;
          v6 = (wchar_t *)v14;
        }
        else
        {
          if ( v10 == 3 )
          {
            v18 = 0;
            if ( (unsigned int)BasepGetVolumeDosLetterNameFromNTName(v14, &pszSrc) )
            {
LABEL_32:
              v6 = (wchar_t *)pszSrc;
              goto LABEL_39;
            }
LABEL_37:
            v6 = (wchar_t *)pszSrc;
            goto LABEL_20;
          }
          v18 = 0;
        }
LABEL_39:
        if ( (a4 & 8) == 0 )
        {
          Str = 0;
          BaseAddress = 0;
          v19 = 0;
          if ( (unsigned int)BasepGetFileNameInformation(Handle, FileNormalizedNameInformation) )
          {
            RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v7);
            v7 = Str;
          }
          else
          {
            if ( LODWORD(KeGetPcr()->Unused1[0]) != 87
              && LODWORD(KeGetPcr()->Unused1[0]) != 124
              && LODWORD(KeGetPcr()->Unused1[0]) != 50 )
            {
              goto LABEL_20;
            }
            if ( (v37 & 0xFFFFFFFD) != 0 )
              goto LABEL_51;
            if ( !(unsigned int)BasepGetVolumeDosLetterNameFromNTName(v6, &BaseAddress)
              && LODWORD(KeGetPcr()->Unused1[0]) == 8 )
            {
              goto LABEL_20;
            }
            v19 = (wchar_t *)BaseAddress;
            if ( BaseAddress )
              goto LABEL_50;
            if ( !(unsigned int)BasepGetVolumeGUIDFromNTName(v6, &BaseAddress) )
              goto LABEL_20;
            v19 = (wchar_t *)BaseAddress;
            if ( BaseAddress )
LABEL_50:
              v20 = v19;
            else
LABEL_51:
              v20 = v6;
            v21 = wcslen(v20);
            v38 = 2 * (v21 + a3 + wcslen(v7)) + 2;
            Heap = (wchar_t *)RtlAllocateHeap(
                                *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                                KernelBaseGlobalData,
                                v38);
            v23 = Heap;
            if ( !Heap )
            {
              if ( v19 )
                RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v19);
LABEL_55:
              v16 = 8;
              goto LABEL_27;
            }
            v24 = v6;
            if ( v19 )
              v24 = v19;
            v25 = (unsigned __int64)v38 >> 1;
            StringCchCopyW(Heap, v25, v24);
            StringCchCatW(v23, v25, v7);
            v39 = v38 >> 1;
            LongPathNameW = GetLongPathNameW(v23, v23);
            if ( !LongPathNameW )
            {
              RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v23);
              if ( v19 )
                RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v19);
              goto LABEL_20;
            }
            if ( LongPathNameW >= v39 )
            {
              if ( v19 )
              {
                v27 = LongPathNameW - wcslen(v19);
                if ( v6 )
                  v28 = wcslen(v6);
                else
                  v28 = 0;
                LongPathNameW = v28 + v27;
                RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v19);
              }
              v5 = LongPathNameW + 1;
              RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v23);
              v16 = 0;
              goto LABEL_27;
            }
            v29 = v19;
            if ( !v19 )
              v29 = v6;
            v30 = (unsigned int)wcslen(v29);
            v31 = wcslen(v23);
            memmove_0(v23, &v23[v30], 2 * (1 - v30 + v31));
            v18 = 0;
            if ( v19 )
              RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v19);
            RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v7);
            v7 = v23;
          }
        }
        if ( v6 )
          v18 = wcslen(v6);
        v32 = wcslen(v7);
        v5 = v32 + v18 + 1;
        if ( v5 <= a3 )
        {
          v5 = v32 + v18;
          v33 = a3;
          *a2 = 0;
          if ( v6 )
            StringCchCopyW(a2, a3, v6);
          StringCchCatW(a2, v33, v7);
          goto LABEL_20;
        }
        goto LABEL_55;
      }
      v18 = 0;
      if ( (unsigned int)BasepGetVolumeGUIDFromNTName(v14, &pszSrc) )
        goto LABEL_32;
      if ( LODWORD(KeGetPcr()->Unused1[0]) == 1 )
        RtlSetLastWin32Error(3u);
      goto LABEL_37;
    }
  }
LABEL_20:
  if ( v7 )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v7);
  if ( v6 )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v6);
  return v5;
}

```

## disassembly

```asm
0x140019a5c  mov     [rsp-40h+arg_18], r9d
0x140019a61  mov     dword ptr [rsp-40h+cchDest], r8d
0x140019a66  mov     [rsp-40h+pszDest], rdx
0x140019a6b  push    rbp
0x140019a6c  push    rbx
0x140019a6d  push    rsi
0x140019a6e  push    rdi
0x140019a6f  push    r12
0x140019a71  push    r13
0x140019a73  push    r14
0x140019a75  push    r15
0x140019a77  mov     rbp, rsp
0x140019a7a  sub     rsp, 48h
0x140019a7e  xor     ebx, ebx
0x140019a80  mov     r10d, r9d
0x140019a83  mov     [rbp+pszSrc], rbx
0x140019a87  mov     r12, rcx
0x140019a8a  mov     [rbp+Str], rbx
0x140019a8e  mov     r13d, ebx
0x140019a91  mov     [rbp+BaseAddress], rbx
0x140019a95  mov     esi, ebx
0x140019a97  mov     r15d, ebx
0x140019a9a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140019a9e  jnz     short loc_140019AAE
0x140019aa0  lea     ecx, [rbx+6]; LastError
0x140019aa3  call    cs:__imp_RtlSetLastWin32Error
0x140019aa9  jmp     loc_140019B97
0x140019aae  mov     r9d, 1
0x140019ab4  mov     edx, r10d
0x140019ab7  and     edx, r9d
0x140019aba  mov     eax, r10d
0x140019abd  mov     r8d, edx
0x140019ac0  mov     edi, ebx
0x140019ac2  lea     ecx, [r9+1]
0x140019ac6  and     eax, ecx
0x140019ac8  cmovnz  r8d, ecx
0x140019acc  test    eax, eax
0x140019ace  lea     ecx, [r9+rdx]
0x140019ad2  cmovz   cx, dx
0x140019ad6  bt      r10d, 2
0x140019adb  cmovnb  edi, r8d
0x140019adf  lea     edx, [r9+rcx]
0x140019ae3  cmovnb  dx, cx
0x140019ae7  cmp     dx, r9w
0x140019aeb  jbe     short loc_140019AF3
0x140019aed  lea     ecx, [r9+56h]
0x140019af1  jmp     short loc_140019AA3
0x140019af3  test    dx, dx
0x140019af6  mov     eax, 3
0x140019afb  lea     rdx, [rbp+BaseAddress]
0x140019aff  mov     rcx, r12; Handle
0x140019b02  cmovz   edi, eax
0x140019b05  mov     dword ptr [rbp+arg_0], edi
0x140019b08  call    BasepGetObjectNTName
0x140019b0d  test    eax, eax
0x140019b0f  jz      short loc_140019B3C
0x140019b11  lea     r8, [rbp+Str]
0x140019b15  mov     edx, 9; FileInformationClass
0x140019b1a  mov     rcx, r12; FileHandle
0x140019b1d  call    BasepGetFileNameInformation
0x140019b22  mov     r15, [rbp+Str]
0x140019b26  test    eax, eax
0x140019b28  jz      short loc_140019B3C
0x140019b2a  cmp     word ptr [r15], 5Ch ; '\'
0x140019b2f  jz      short loc_140019BAB
0x140019b31  mov     ecx, 5; LastError
0x140019b36  call    cs:__imp_RtlSetLastWin32Error
0x140019b3c  mov     r14, [rbp+BaseAddress]
0x140019b40  test    r14, r14
0x140019b43  jz      short loc_140019B5D
0x140019b45  mov     rcx, gs:60h
0x140019b4e  mov     r8, r14; BaseAddress
0x140019b51  xor     edx, edx; Flags
0x140019b53  mov     rcx, [rcx+30h]; HeapHandle
0x140019b57  call    cs:__imp_RtlFreeHeap
0x140019b5d  test    r15, r15
0x140019b60  jz      short loc_140019B7A
0x140019b62  mov     rcx, gs:60h
0x140019b6b  mov     r8, r15; BaseAddress
0x140019b6e  xor     edx, edx; Flags
0x140019b70  mov     rcx, [rcx+30h]; HeapHandle
0x140019b74  call    cs:__imp_RtlFreeHeap
0x140019b7a  test    rsi, rsi
0x140019b7d  jz      short loc_140019B97
0x140019b7f  mov     rcx, gs:60h
0x140019b88  mov     r8, rsi; BaseAddress
0x140019b8b  xor     edx, edx; Flags
0x140019b8d  mov     rcx, [rcx+30h]; HeapHandle
0x140019b91  call    cs:__imp_RtlFreeHeap
0x140019b97  mov     eax, r13d
0x140019b9a  add     rsp, 48h
0x140019b9e  pop     r15
0x140019ba0  pop     r14
0x140019ba2  pop     r13
0x140019ba4  pop     r12
0x140019ba6  pop     rdi
0x140019ba7  pop     rsi
0x140019ba8  pop     rbx
0x140019ba9  pop     rbp
0x140019baa  retn
0x140019bab  mov     r14, [rbp+BaseAddress]
0x140019baf  mov     rcx, r14; Str
0x140019bb2  call    cs:__imp_wcslen
0x140019bb8  mov     rcx, r15; Str
0x140019bbb  mov     rbx, rax
0x140019bbe  call    cs:__imp_wcslen
0x140019bc4  cmp     rax, rbx
0x140019bc7  jb      short loc_140019BD9
0x140019bc9  mov     ecx, 0A1h; LastError
0x140019bce  call    cs:__imp_RtlSetLastWin32Error
0x140019bd4  jmp     loc_140019B40
0x140019bd9  mov     rcx, r14; Str
0x140019bdc  call    cs:__imp_wcslen
0x140019be2  mov     rcx, r15; Str
0x140019be5  mov     rbx, rax
0x140019be8  call    cs:__imp_wcslen
0x140019bee  sub     rbx, rax
0x140019bf1  xor     ecx, ecx
0x140019bf3  mov     eax, edi
0x140019bf5  mov     [r14+rbx*2], cx
0x140019bfa  sub     eax, 1
0x140019bfd  jz      short loc_140019C2B
0x140019bff  sub     eax, 1
0x140019c02  jz      short loc_140019C21
0x140019c04  cmp     eax, 1
0x140019c07  jnz     short loc_140019C5E
0x140019c09  lea     rdx, [rbp+pszSrc]
0x140019c0d  mov     rcx, r14; Src
0x140019c10  call    BasepGetVolumeDosLetterNameFromNTName
0x140019c15  xor     ebx, ebx
0x140019c17  test    eax, eax
0x140019c19  jz      short loc_140019C55
0x140019c1b  mov     rsi, [rbp+pszSrc]
0x140019c1f  jmp     short loc_140019C60
0x140019c21  xor     ebx, ebx
0x140019c23  mov     rsi, r14
0x140019c26  mov     r14d, ebx
0x140019c29  jmp     short loc_140019C60
0x140019c2b  lea     rdx, [rbp+pszSrc]
0x140019c2f  mov     rcx, r14; Src
0x140019c32  call    BasepGetVolumeGUIDFromNTName
0x140019c37  xor     ebx, ebx
0x140019c39  test    eax, eax
0x140019c3b  jnz     short loc_140019C1B
0x140019c3d  mov     eax, gs:68h
0x140019c45  lea     edx, [rbx+1]
0x140019c48  cmp     eax, edx
0x140019c4a  jnz     short loc_140019C55
0x140019c4c  lea     ecx, [rbx+3]; LastError
0x140019c4f  call    cs:__imp_RtlSetLastWin32Error
0x140019c55  mov     rsi, [rbp+pszSrc]
0x140019c59  jmp     loc_140019B40
0x140019c5e  xor     ebx, ebx
0x140019c60  test    byte ptr [rbp+arg_18], 8
0x140019c64  jnz     loc_140019F03
0x140019c6a  lea     r8, [rbp+Str]
0x140019c6e  mov     [rbp+Str], rbx
0x140019c72  mov     edx, 30h ; '0'; FileInformationClass
0x140019c77  mov     [rbp+BaseAddress], rbx
0x140019c7b  mov     rcx, r12; FileHandle
0x140019c7e  mov     rdi, rbx
0x140019c81  call    BasepGetFileNameInformation
0x140019c86  test    eax, eax
0x140019c88  jnz     loc_140019EE7
0x140019c8e  mov     eax, gs:68h
0x140019c96  cmp     eax, 57h ; 'W'
0x140019c99  jz      short loc_140019CB9
0x140019c9b  mov     eax, gs:68h
0x140019ca3  cmp     eax, 7Ch ; '|'
0x140019ca6  jz      short loc_140019CB9
0x140019ca8  mov     eax, gs:68h
0x140019cb0  cmp     eax, 32h ; '2'
0x140019cb3  jnz     loc_140019B40
0x140019cb9  test    dword ptr [rbp+arg_0], 0FFFFFFFDh
0x140019cc0  jnz     short loc_140019D1C
0x140019cc2  test    r14, r14
0x140019cc5  lea     rdx, [rbp+BaseAddress]
0x140019cc9  mov     rcx, rsi
0x140019ccc  cmovnz  rcx, r14; Src
0x140019cd0  call    BasepGetVolumeDosLetterNameFromNTName
0x140019cd5  test    eax, eax
0x140019cd7  jnz     short loc_140019CEA
0x140019cd9  mov     eax, gs:68h
0x140019ce1  cmp     eax, 8
0x140019ce4  jz      loc_140019B40
0x140019cea  mov     rdi, [rbp+BaseAddress]
0x140019cee  test    rdi, rdi
0x140019cf1  jnz     short loc_140019D17
0x140019cf3  test    r14, r14
0x140019cf6  lea     rdx, [rbp+BaseAddress]
0x140019cfa  mov     rcx, rsi
0x140019cfd  cmovnz  rcx, r14; Src
0x140019d01  call    BasepGetVolumeGUIDFromNTName
0x140019d06  test    eax, eax
0x140019d08  jz      loc_140019B40
0x140019d0e  mov     rdi, [rbp+BaseAddress]
0x140019d12  test    rdi, rdi
0x140019d15  jz      short loc_140019D1C
0x140019d17  mov     rcx, rdi
0x140019d1a  jmp     short loc_140019D1F
0x140019d1c  mov     rcx, rsi; Str
0x140019d1f  call    cs:__imp_wcslen
0x140019d25  mov     rcx, r15; Str
0x140019d28  mov     rbx, rax
0x140019d2b  call    cs:__imp_wcslen
0x140019d31  mov     ecx, dword ptr [rbp+cchDest]
0x140019d34  add     ecx, ebx
0x140019d36  add     eax, ecx
0x140019d38  mov     rcx, gs:60h
0x140019d41  mov     edx, cs:KernelBaseGlobalData; Flags
0x140019d47  mov     rcx, [rcx+30h]; HeapHandle
0x140019d4b  lea     eax, ds:2[rax*2]
0x140019d52  mov     r8d, eax; Size
0x140019d55  mov     dword ptr [rbp+arg_0], eax
0x140019d58  mov     ebx, eax
0x140019d5a  call    cs:__imp_RtlAllocateHeap
0x140019d60  mov     r12, rax
0x140019d63  test    rax, rax
0x140019d66  jnz     short loc_140019D8F
0x140019d68  test    rdi, rdi
0x140019d6b  jz      short loc_140019D85
0x140019d6d  mov     rcx, gs:60h
0x140019d76  mov     r8, rdi; BaseAddress
0x140019d79  xor     edx, edx; Flags
0x140019d7b  mov     rcx, [rcx+30h]; HeapHandle
0x140019d7f  call    cs:__imp_RtlFreeHeap
0x140019d85  mov     ecx, 8
0x140019d8a  jmp     loc_140019BCE
0x140019d8f  test    rdi, rdi
0x140019d92  mov     r8, rsi
0x140019d95  mov     rcx, r12; pszDest
0x140019d98  cmovnz  r8, rdi; pszSrc
0x140019d9c  shr     rbx, 1
0x140019d9f  mov     rdx, rbx; cchDest
0x140019da2  call    StringCchCopyW
0x140019da7  mov     r8, r15; pszSrc
0x140019daa  mov     rdx, rbx; cchDest
0x140019dad  mov     rcx, r12; pszDest
0x140019db0  call    StringCchCatW
0x140019db5  mov     eax, dword ptr [rbp+arg_0]
0x140019db8  mov     rdx, r12; void *
0x140019dbb  shr     eax, 1
0x140019dbd  mov     rcx, r12; Name
0x140019dc0  mov     r8d, eax
0x140019dc3  mov     [rbp+arg_0], rax
0x140019dc7  call    GetLongPathNameW
0x140019dcc  mov     ebx, eax
0x140019dce  test    eax, eax
0x140019dd0  jnz     short loc_140019E10
0x140019dd2  mov     rcx, gs:60h
0x140019ddb  mov     r8, r12; BaseAddress
0x140019dde  xor     edx, edx; Flags
0x140019de0  mov     rcx, [rcx+30h]; HeapHandle
0x140019de4  call    cs:__imp_RtlFreeHeap
0x140019dea  test    rdi, rdi
0x140019ded  jz      loc_140019B40
0x140019df3  mov     rcx, gs:60h
0x140019dfc  mov     r8, rdi; BaseAddress
0x140019dff  xor     edx, edx; Flags
0x140019e01  mov     rcx, [rcx+30h]; HeapHandle
0x140019e05  call    cs:__imp_RtlFreeHeap
0x140019e0b  jmp     loc_140019B40
0x140019e10  cmp     ebx, dword ptr [rbp+arg_0]
0x140019e13  jb      short loc_140019E74
0x140019e15  test    rdi, rdi
0x140019e18  jz      short loc_140019E51
0x140019e1a  mov     rcx, rdi; Str
0x140019e1d  call    cs:__imp_wcslen
0x140019e23  sub     ebx, eax
0x140019e25  test    rsi, rsi
0x140019e28  jz      short loc_140019E35
0x140019e2a  mov     rcx, rsi; Str
0x140019e2d  call    cs:__imp_wcslen
0x140019e33  jmp     short loc_140019E37
0x140019e35  xor     eax, eax
0x140019e37  mov     rcx, gs:60h
0x140019e40  add     ebx, eax
0x140019e42  mov     r8, rdi; BaseAddress
0x140019e45  xor     edx, edx; Flags
0x140019e47  mov     rcx, [rcx+30h]; HeapHandle
0x140019e4b  call    cs:__imp_RtlFreeHeap
0x140019e51  mov     rcx, gs:60h
0x140019e5a  lea     r13d, [rbx+1]
0x140019e5e  mov     r8, r12; BaseAddress
0x140019e61  xor     edx, edx; Flags
0x140019e63  mov     rcx, [rcx+30h]; HeapHandle
0x140019e67  call    cs:__imp_RtlFreeHeap
0x140019e6d  xor     ecx, ecx
0x140019e6f  jmp     loc_140019BCE
0x140019e74  mov     rcx, rdi
0x140019e77  test    rdi, rdi
0x140019e7a  jnz     short loc_140019E7F
0x140019e7c  mov     rcx, rsi; Str
0x140019e7f  call    cs:__imp_wcslen
0x140019e85  mov     rcx, r12; Str
0x140019e88  mov     ebx, eax
0x140019e8a  call    cs:__imp_wcslen
0x140019e90  mov     edx, 1
0x140019e95  mov     rcx, r12; void *
0x140019e98  sub     rdx, rbx
  ... truncated ...
```
