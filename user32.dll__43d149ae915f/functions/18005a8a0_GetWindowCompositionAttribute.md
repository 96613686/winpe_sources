# GetWindowCompositionAttribute

- ea: `0x18005a8a0`
- end: `0x18005aa54`
- name: `GetWindowCompositionAttribute`
- size: `436`
- prototype: `__int64 __fastcall(HWND)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d210`
- `0x18005a8a0`

## import_xrefs

- `win32u!NtUserGetWindowCompositionAttribute` at `0x18005a976`
- `win32u!NtUserGetWindowCompositionAttribute` at `0x18005a976`
- `ntdll!RtlSetLastWin32Error` at `0x18005a938`
- `ntdll!RtlSetLastWin32Error` at `0x18005a938`
- `ntdll!RtlNtStatusToDosError` at `0x18005aa31`
- `ntdll!RtlNtStatusToDosError` at `0x18005aa31`

## pseudocode

```c
__int64 __fastcall GetWindowCompositionAttribute(HWND a1, int *a2)
{
  struct tagWND *v4; // rax
  struct tagWND *v5; // rdx
  int v6; // ecx
  unsigned int v7; // eax
  int v8; // r8d
  __int64 result; // rax
  ULONG v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  bool v17; // zf
  __int64 v18; // r9
  char v19; // dl
  int v20; // r8d
  __int64 v21; // rax
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx

  if ( !a2 || !*((_QWORD *)a2 + 1) || !*a2 || *a2 >= 38 )
    goto LABEL_12;
  if ( (unsigned int)a2[4] < (unsigned __int64)qword_1800AAA78[2 * *a2] )
  {
    v10 = RtlNtStatusToDosError(-1073741789);
    goto LABEL_13;
  }
  v4 = ValidateHwnd(a1);
  v5 = v4;
  if ( !v4 )
  {
    v10 = 6;
    goto LABEL_13;
  }
  v6 = *a2;
  if ( *a2 != 18 )
  {
    if ( v6 > 13 )
    {
      v22 = v6 - 14;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( v23 )
        {
          v24 = v23 - 1;
          if ( v24 )
          {
            v25 = v24 - 1;
            if ( v25 )
            {
              v26 = v25 - 2;
              if ( v26 )
              {
                v27 = v26 - 9;
                if ( v27 )
                {
                  v17 = v27 == 5;
LABEL_23:
                  if ( !v17 )
                    return NtUserGetWindowCompositionAttribute(a1, a2);
                }
              }
            }
          }
        }
      }
    }
    else if ( v6 != 13 )
    {
      v11 = v6 - 2;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 2;
            if ( v14 )
            {
              v15 = v14 - 1;
              if ( v15 )
              {
                v16 = v15 - 2;
                if ( v16 )
                {
                  v17 = v16 == 2;
                  goto LABEL_23;
                }
              }
            }
          }
        }
      }
    }
LABEL_12:
    v10 = 87;
LABEL_13:
    RtlSetLastWin32Error(v10);
    return 0;
  }
  v7 = *((unsigned __int8 *)v4 + 233);
  v8 = (v7 >> 6) & 1 | 2;
  if ( (v7 & 0x20) == 0 )
    v8 = (v7 >> 6) & 1;
  if ( !v8 && (*((_BYTE *)v5 + 31) & 0xC0) == 0x40 )
  {
    v18 = *((_QWORD *)v5 + 6);
    if ( v18 )
      v18 = (__int64)v5 + v18 - *((_QWORD *)v5 + 1);
    while ( v18 && (*(_WORD *)(v18 + 42) & 0x2FFF) != 0x29D )
    {
      v19 = *(_BYTE *)(v18 + 233);
      v20 = ((v19 & 0x40) != 0) | 2;
      if ( (v19 & 0x20) == 0 )
        v20 = (v19 & 0x40) != 0;
      if ( v20 )
      {
        v8 = v20 | 4;
        break;
      }
      v21 = *(_QWORD *)(v18 + 48);
      if ( v21 )
        v18 += v21 - *(_QWORD *)(v18 + 8);
      else
        v18 = 0;
      v8 = 0;
    }
  }
  result = 1;
  **((_DWORD **)a2 + 1) = v8;
  return result;
}

```

## disassembly

```asm
0x18005a8a0  mov     [rsp+arg_0], rbx
0x18005a8a5  push    rdi
0x18005a8a6  sub     rsp, 20h
0x18005a8aa  mov     rbx, rdx
0x18005a8ad  mov     rdi, rcx
0x18005a8b0  test    rdx, rdx
0x18005a8b3  jz      short loc_18005A933
0x18005a8b5  cmp     qword ptr [rdx+8], 0
0x18005a8ba  jz      short loc_18005A933
0x18005a8bc  cmp     dword ptr [rdx], 0
0x18005a8bf  jz      short loc_18005A933
0x18005a8c1  cmp     dword ptr [rdx], 26h ; '&'
0x18005a8c4  jge     short loc_18005A933
0x18005a8c6  movsxd  rcx, dword ptr [rdx]
0x18005a8c9  lea     rdx, qword_1800AAA78
0x18005a8d0  mov     eax, [rbx+10h]
0x18005a8d3  add     rcx, rcx
0x18005a8d6  cmp     rax, [rdx+rcx*8]
0x18005a8da  jb      loc_18005AA2C
0x18005a8e0  mov     rcx, rdi; HWND
0x18005a8e3  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x18005a8e8  mov     rdx, rax
0x18005a8eb  test    rax, rax
0x18005a8ee  jz      loc_18005AA3E
0x18005a8f4  mov     ecx, [rbx]
0x18005a8f6  cmp     ecx, 12h
0x18005a8f9  jnz     short loc_18005A942
0x18005a8fb  movzx   eax, byte ptr [rax+0E9h]
0x18005a902  mov     ecx, eax
0x18005a904  shr     ecx, 6
0x18005a907  and     ecx, 1
0x18005a90a  mov     r8d, ecx
0x18005a90d  or      r8d, 2
0x18005a911  test    al, 20h
0x18005a913  cmovz   r8d, ecx
0x18005a917  test    r8d, r8d
0x18005a91a  jz      short loc_18005A97E
0x18005a91c  mov     rcx, [rbx+8]
0x18005a920  mov     eax, 1
0x18005a925  mov     [rcx], r8d
0x18005a928  mov     rbx, [rsp+28h+arg_0]
0x18005a92d  add     rsp, 20h
0x18005a931  pop     rdi
0x18005a932  retn
0x18005a933  mov     ecx, 57h ; 'W'; LastError
0x18005a938  call    cs:__imp_RtlSetLastWin32Error
0x18005a93e  xor     eax, eax
0x18005a940  jmp     short loc_18005A928
0x18005a942  cmp     ecx, 0Dh
0x18005a945  jg      loc_18005A9EE
0x18005a94b  jz      short loc_18005A933
0x18005a94d  sub     ecx, 2
0x18005a950  jz      short loc_18005A933
0x18005a952  sub     ecx, 1
0x18005a955  jz      short loc_18005A933
0x18005a957  sub     ecx, 1
0x18005a95a  jz      short loc_18005A933
0x18005a95c  sub     ecx, 2
0x18005a95f  jz      short loc_18005A933
0x18005a961  sub     ecx, 1
0x18005a964  jz      short loc_18005A933
0x18005a966  sub     ecx, 2
0x18005a969  jz      short loc_18005A933
0x18005a96b  cmp     ecx, 2
0x18005a96e  jz      short loc_18005A933
0x18005a970  mov     rdx, rbx
0x18005a973  mov     rcx, rdi
0x18005a976  call    cs:__imp_NtUserGetWindowCompositionAttribute
0x18005a97c  jmp     short loc_18005A928
0x18005a97e  mov     al, [rdx+1Fh]
0x18005a981  and     al, 0C0h
0x18005a983  cmp     al, 40h ; '@'
0x18005a985  jnz     short loc_18005A91C
0x18005a987  mov     r9, [rdx+30h]
0x18005a98b  test    r9, r9
0x18005a98e  jnz     loc_18005AA48
0x18005a994  test    r9, r9
0x18005a997  jz      short loc_18005A91C
0x18005a999  movzx   eax, word ptr [r9+2Ah]
0x18005a99e  and     eax, 0FFFF2FFFh
0x18005a9a3  cmp     eax, 29Dh
0x18005a9a8  jz      loc_18005A91C
0x18005a9ae  mov     dl, [r9+0E9h]
0x18005a9b5  mov     ecx, r8d
0x18005a9b8  or      ecx, 1
0x18005a9bb  test    dl, 40h
0x18005a9be  cmovz   ecx, r8d
0x18005a9c2  mov     r8d, ecx
0x18005a9c5  or      r8d, 2
0x18005a9c9  test    dl, 20h
0x18005a9cc  cmovz   r8d, ecx
0x18005a9d0  test    r8d, r8d
0x18005a9d3  jnz     loc_18009FCF1
0x18005a9d9  mov     rax, [r9+30h]
0x18005a9dd  test    rax, rax
0x18005a9e0  jnz     loc_18009FCE2
0x18005a9e6  xor     r9d, r9d
0x18005a9e9  jmp     loc_18009FCE9
0x18005a9ee  sub     ecx, 0Eh
0x18005a9f1  jz      loc_18005A933
0x18005a9f7  sub     ecx, 1
0x18005a9fa  jz      loc_18005A933
0x18005aa00  sub     ecx, 1
0x18005aa03  jz      loc_18005A933
0x18005aa09  sub     ecx, 1
0x18005aa0c  jz      loc_18005A933
0x18005aa12  sub     ecx, 2
0x18005aa15  jz      loc_18005A933
0x18005aa1b  sub     ecx, 9
0x18005aa1e  jz      loc_18005A933
0x18005aa24  cmp     ecx, 5
0x18005aa27  jmp     loc_18005A96E
0x18005aa2c  mov     ecx, 0C0000023h; Status
0x18005aa31  call    cs:__imp_RtlNtStatusToDosError
0x18005aa37  mov     ecx, eax
0x18005aa39  jmp     loc_18005A938
0x18005aa3e  mov     ecx, 6
0x18005aa43  jmp     loc_18005A938
0x18005aa48  sub     r9, [rdx+8]
0x18005aa4c  add     r9, rdx
0x18005aa4f  jmp     loc_18005A994
0x18009fce2  sub     rax, [r9+8]
0x18009fce6  add     r9, rax
0x18009fce9  xor     r8d, r8d
0x18009fcec  jmp     loc_18005A994
0x18009fcf1  or      r8d, 4
0x18009fcf5  jmp     loc_18005A91C
```
