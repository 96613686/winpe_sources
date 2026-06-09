# xxxCBSetEditItemHeight(tagCBox *,int)

- ea: `0x180076c00`
- end: `0x180076d36`
- name: `?xxxCBSetEditItemHeight@@YAJPEAUtagCBox@@H@Z`
- size: `310`
- prototype: `__int64 __fastcall(struct tagCBox *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180057fa0`

## callees

- `0x180076c00`

## import_xrefs

- `win32u!NtUserSetWindowPos` at `0x180076d28`
- `win32u!NtUserSetWindowPos` at `0x180076d28`
- `win32u!NtUserMoveWindow` at `0x180076c73`
- `win32u!NtUserMoveWindow` at `0x180076cab`
- `win32u!NtUserMoveWindow` at `0x180076cfe`
- `win32u!NtUserMoveWindow` at `0x180076c73`
- `win32u!NtUserMoveWindow` at `0x180076cab`
- `win32u!NtUserMoveWindow` at `0x180076cfe`
- `ntdll!RtlSetLastWin32Error` at `0x180076c19`
- `ntdll!RtlSetLastWin32Error` at `0x180076c19`

## pseudocode

```c
__int64 __fastcall xxxCBSetEditItemHeight(struct tagCBox *a1, int a2)
{
  bool v4; // zf
  unsigned int v5; // r10d
  _QWORD *v6; // rcx
  _QWORD *v7; // rcx
  __int64 v8; // r9

  if ( a2 <= 255 )
  {
    v4 = (*((_BYTE *)a1 + 80) & 2) == 0;
    v5 = *((_DWORD *)a1 + 5);
    *((_DWORD *)a1 + 7) = v5 + a2;
    *((_DWORD *)a1 + 13) = v5 + a2 + 3;
    if ( !v4 )
      *((_DWORD *)a1 + 11) = v5 + a2 + 1;
    if ( (*((_DWORD *)a1 + 20) & 0x4000) == 0 )
    {
      v6 = (_QWORD *)*((_QWORD *)a1 + 8);
      if ( v6 )
        NtUserMoveWindow(
          *v6,
          *((unsigned int *)a1 + 4),
          v5,
          (unsigned int)(*((_DWORD *)a1 + 6) - *((_DWORD *)a1 + 4)),
          a2,
          1);
    }
    v7 = (_QWORD *)*((_QWORD *)a1 + 9);
    if ( (*((_DWORD *)a1 + 20) & 3) == 1 )
    {
      if ( v7 )
      {
        NtUserMoveWindow(*v7, 0, *((unsigned int *)a1 + 13), *((unsigned int *)a1 + 12), *((_DWORD *)a1 + 15), 0);
        NtUserSetWindowPos(
          **(_QWORD **)a1,
          0,
          0,
          0,
          *((_DWORD *)a1 + 12),
          *((_DWORD *)a1 + 13) + *(_DWORD *)(*((_QWORD *)a1 + 9) + 100LL) - *(_DWORD *)(*((_QWORD *)a1 + 9) + 92LL),
          22);
      }
    }
    else
    {
      if ( v7 )
      {
        v8 = *((unsigned int *)a1 + 14);
        if ( (int)v8 <= *((_DWORD *)a1 + 12) )
          v8 = *((unsigned int *)a1 + 12);
        NtUserMoveWindow(
          *v7,
          *(unsigned int *)(*(_QWORD *)a1 + 88LL),
          (unsigned int)(*((_DWORD *)a1 + 13) + *(_DWORD *)(*(_QWORD *)a1 + 92LL)),
          v8,
          *((_DWORD *)a1 + 15),
          0);
      }
      NtUserSetWindowPos(**(_QWORD **)a1, 0, 0, 0, *((_DWORD *)a1 + 12), *((_DWORD *)a1 + 13), 22);
    }
    return 0;
  }
  else
  {
    RtlSetLastWin32Error(0x590u);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x180076c00  push    rbx
0x180076c02  sub     rsp, 40h
0x180076c06  mov     r8d, edx
0x180076c09  mov     rbx, rcx
0x180076c0c  cmp     edx, 0FFh
0x180076c12  jle     short loc_180076C27
0x180076c14  mov     ecx, 590h; LastError
0x180076c19  call    cs:__imp_RtlSetLastWin32Error
0x180076c1f  or      eax, 0FFFFFFFFh
0x180076c22  jmp     loc_180076D30
0x180076c27  test    byte ptr [rbx+50h], 2
0x180076c2b  mov     r10d, [rcx+14h]
0x180076c2f  lea     ecx, [r10+rdx]
0x180076c33  lea     eax, [rcx+3]
0x180076c36  mov     [rbx+1Ch], ecx
0x180076c39  mov     [rbx+34h], eax
0x180076c3c  jz      short loc_180076C44
0x180076c3e  lea     eax, [rcx+1]
0x180076c41  mov     [rbx+2Ch], eax
0x180076c44  test    dword ptr [rbx+50h], 4000h
0x180076c4b  jnz     short loc_180076C79
0x180076c4d  mov     rcx, [rbx+40h]
0x180076c51  test    rcx, rcx
0x180076c54  jz      short loc_180076C79
0x180076c56  mov     r9d, [rbx+18h]
0x180076c5a  mov     edx, [rbx+10h]
0x180076c5d  sub     r9d, edx
0x180076c60  mov     rcx, [rcx]
0x180076c63  mov     [rsp+48h+var_20], 1
0x180076c6b  mov     [rsp+48h+var_28], r8d
0x180076c70  mov     r8d, r10d
0x180076c73  call    cs:__imp_NtUserMoveWindow
0x180076c79  mov     eax, [rbx+50h]
0x180076c7c  mov     rcx, [rbx+48h]
0x180076c80  and     al, 3
0x180076c82  cmp     al, 1
0x180076c84  jnz     short loc_180076CCC
0x180076c86  test    rcx, rcx
0x180076c89  jz      loc_180076D2E
0x180076c8f  mov     eax, [rbx+3Ch]
0x180076c92  xor     edx, edx
0x180076c94  mov     r9d, [rbx+30h]
0x180076c98  mov     r8d, [rbx+34h]
0x180076c9c  mov     rcx, [rcx]
0x180076c9f  mov     [rsp+48h+var_20], 0
0x180076ca7  mov     [rsp+48h+var_28], eax
0x180076cab  call    cs:__imp_NtUserMoveWindow
0x180076cb1  mov     rax, [rbx+48h]
0x180076cb5  mov     [rsp+48h+var_18], 16h
0x180076cbd  mov     edx, [rax+64h]
0x180076cc0  sub     edx, [rax+5Ch]
0x180076cc3  add     edx, [rbx+34h]
0x180076cc6  mov     [rsp+48h+var_20], edx
0x180076cca  jmp     short loc_180076D13
0x180076ccc  test    rcx, rcx
0x180076ccf  jz      short loc_180076D04
0x180076cd1  mov     rdx, [rbx]
0x180076cd4  mov     r9d, [rbx+38h]
0x180076cd8  cmp     r9d, [rbx+30h]
0x180076cdc  mov     eax, [rbx+3Ch]
0x180076cdf  mov     r8d, [rdx+5Ch]
0x180076ce3  cmovle  r9d, [rbx+30h]
0x180076ce8  add     r8d, [rbx+34h]
0x180076cec  mov     edx, [rdx+58h]
0x180076cef  mov     rcx, [rcx]
0x180076cf2  mov     [rsp+48h+var_20], 0
0x180076cfa  mov     [rsp+48h+var_28], eax
0x180076cfe  call    cs:__imp_NtUserMoveWindow
0x180076d04  mov     eax, [rbx+34h]
0x180076d07  mov     [rsp+48h+var_18], 16h
0x180076d0f  mov     [rsp+48h+var_20], eax
0x180076d13  mov     rcx, [rbx]
0x180076d16  xor     r9d, r9d
0x180076d19  mov     eax, [rbx+30h]
0x180076d1c  xor     r8d, r8d
0x180076d1f  xor     edx, edx
0x180076d21  mov     [rsp+48h+var_28], eax
0x180076d25  mov     rcx, [rcx]
0x180076d28  call    cs:__imp_NtUserSetWindowPos
0x180076d2e  xor     eax, eax
0x180076d30  add     rsp, 40h
0x180076d34  pop     rbx
0x180076d35  retn
```
