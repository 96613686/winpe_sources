# ProcessRegistrationMessage(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180019c04`
- end: `0x180019d1e`
- name: `?ProcessRegistrationMessage@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `282`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180019b90`

## callees

- `0x18000bd00`
- `0x1800198dc`
- `0x180019b20`
- `0x180019c04`
- `0x180019d30`
- `0x18001a004`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180019c3d`
- `ntdll!RtlEnterCriticalSection` at `0x180019c3d`
- `ntdll!RtlLeaveCriticalSection` at `0x180019cec`
- `ntdll!RtlLeaveCriticalSection` at `0x180019cec`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180019ccc`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180019cd5`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180019ccc`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180019cd5`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180019cdf`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180019cdf`

## pseudocode

```c
__int64 __fastcall ProcessRegistrationMessage(HWND hWnd, __int64 a2, unsigned __int16 a3, __int64 a4)
{
  int v4; // ebp
  HWND *v7; // rax
  HWND v8; // rbx
  LONG_PTR WindowLongPtrW; // rax
  struct tagCL_INSTANCE_INFO *v10; // rsi
  bool v11; // zf
  unsigned __int16 v12; // ax
  HSZ v13; // rdi
  ATOM InstSpecificAtom; // bx
  unsigned __int16 v15; // dx

  v4 = a2;
  LOBYTE(a2) = 1;
  v7 = (HWND *)HMValidateHandleNoRip(a4, a2);
  if ( v7 )
  {
    v8 = *v7;
    if ( *v7 )
    {
      RtlEnterCriticalSection(&gcsDDEML);
      WindowLongPtrW = GetWindowLongPtrW(hWnd, 0);
      v10 = (struct tagCL_INSTANCE_INFO *)WindowLongPtrW;
      if ( WindowLongPtrW )
      {
        if ( v4 == 1224 )
        {
          v11 = (*(_DWORD *)(WindowLongPtrW + 56) & 0x80000) == 0;
        }
        else
        {
          if ( v4 != 1225 )
            goto LABEL_7;
          v11 = (*(_DWORD *)(WindowLongPtrW + 56) & 0x100000) == 0;
        }
        if ( v11 )
        {
LABEL_7:
          v12 = GlobalToLocalAtom(a3);
          v13 = (HSZ)v12;
          InstSpecificAtom = MakeInstSpecificAtom(v12, v8);
          v15 = -32606;
          if ( v4 != 1224 )
            v15 = -32558;
          DoCallback(v10, v15, 0, 0, v13, (HSZ)(InstSpecificAtom | 0x10000LL), 0, 0, 0);
          DeleteAtom((ATOM)v13);
          DeleteAtom(InstSpecificAtom);
        }
      }
      GlobalDeleteAtom(a3);
      RtlLeaveCriticalSection(&gcsDDEML);
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180019c04  push    rbx
0x180019c06  push    rbp
0x180019c07  push    rsi
0x180019c08  push    rdi
0x180019c09  push    r14
0x180019c0b  sub     rsp, 50h
0x180019c0f  mov     ebp, edx
0x180019c11  mov     rdi, rcx
0x180019c14  mov     dl, 1
0x180019c16  mov     rcx, r9
0x180019c19  mov     r14, r8
0x180019c1c  call    HMValidateHandleNoRip
0x180019c21  test    rax, rax
0x180019c24  jz      loc_180019D02
0x180019c2a  mov     rbx, [rax]
0x180019c2d  test    rbx, rbx
0x180019c30  jz      loc_180019D02
0x180019c36  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180019c3d  call    cs:__imp_RtlEnterCriticalSection
0x180019c43  xor     edx, edx; nIndex
0x180019c45  mov     rcx, rdi; hWnd
0x180019c48  call    GetWindowLongPtrW
0x180019c4d  mov     rsi, rax
0x180019c50  test    rax, rax
0x180019c53  jz      loc_180019CDB
0x180019c59  cmp     ebp, 4C8h
0x180019c5f  jnz     loc_180019D06
0x180019c65  test    dword ptr [rax+38h], 80000h
0x180019c6c  jnz     short loc_180019CDB
0x180019c6e  movzx   ecx, r14w; unsigned __int16
0x180019c72  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x180019c77  movzx   edi, ax
0x180019c7a  mov     rdx, rbx; HWND
0x180019c7d  movzx   ecx, di; unsigned __int16
0x180019c80  call    ?MakeInstSpecificAtom@@YAGGPEAUHWND__@@@Z; MakeInstSpecificAtom(ushort,HWND__ *)
0x180019c85  xor     r8d, r8d; unsigned __int16
0x180019c88  movzx   ebx, ax
0x180019c8b  mov     [rsp+78h+var_38], r8; unsigned __int64
0x180019c90  mov     edx, 80A2h
0x180019c95  mov     [rsp+78h+var_40], r8; unsigned __int64
0x180019c9a  mov     r9d, ebx
0x180019c9d  bts     r9, 10h
0x180019ca2  mov     [rsp+78h+hData], r8; hData
0x180019ca7  mov     [rsp+78h+var_50], r9; HSZ
0x180019cac  cmp     ebp, 4C8h
0x180019cb2  lea     ecx, [rdx+30h]
0x180019cb5  mov     [rsp+78h+var_58], rdi; HSZ
0x180019cba  cmovnz  dx, cx; unsigned __int16
0x180019cbe  xor     r9d, r9d; HCONV
0x180019cc1  mov     rcx, rsi; struct tagCL_INSTANCE_INFO *
0x180019cc4  call    ?DoCallback@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@GGPEAUHCONV__@@PEAUHSZ__@@2PEAU1@_K4@Z; DoCallback(tagCL_INSTANCE_INFO *,ushort,ushort,HCONV__ *,HSZ__ *,HSZ__ *,HDDEDATA__ *,unsigned __int64,unsigned __int64)
0x180019cc9  movzx   ecx, di; nAtom
0x180019ccc  call    cs:__imp_DeleteAtom
0x180019cd2  movzx   ecx, bx; nAtom
0x180019cd5  call    cs:__imp_DeleteAtom
0x180019cdb  movzx   ecx, r14w; nAtom
0x180019cdf  call    cs:__imp_GlobalDeleteAtom
0x180019ce5  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180019cec  call    cs:__imp_RtlLeaveCriticalSection
0x180019cf2  mov     eax, 1
0x180019cf7  add     rsp, 50h
0x180019cfb  pop     r14
0x180019cfd  pop     rdi
0x180019cfe  pop     rsi
0x180019cff  pop     rbp
0x180019d00  pop     rbx
0x180019d01  retn
0x180019d02  xor     eax, eax
0x180019d04  jmp     short loc_180019CF7
0x180019d06  cmp     ebp, 4C9h
0x180019d0c  jnz     loc_180019C6E
0x180019d12  test    dword ptr [rax+38h], 100000h
0x180019d19  jmp     loc_180019C6C
```
