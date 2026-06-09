# DigestCheckPacForSidFiltering

- ea: `0x180022bb8`
- end: `0x180022ea7`
- name: `DigestCheckPacForSidFiltering`
- size: `751`
- prototype: `__int64 __fastcall(struct _DIGEST_PARAMETER *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001c8e0`
- `0x18001d5e8`

## callees

- `0x180009770`
- `0x180011fec`
- `0x1800185b8`
- `0x180022940`
- `0x180022bb8`
- `0x180036d94`
- `0x180036ddc`
- `0x180037488`
- `0x180037534`

## pseudocode

```c
__int64 __fastcall DigestCheckPacForSidFiltering(struct _DIGEST_PARAMETER *a1, HLOCAL *a2, unsigned int *a3)
{
  struct _PACTYPE *v3; // rsi
  struct _PACTYPE *v4; // rdi
  unsigned int Size; // r15d
  PVOID *v9; // rcx
  int v10; // ebx
  char *i; // rdx
  __int64 v12; // rdx
  unsigned int j; // edx
  struct _PACTYPE *v14; // r8
  int v15; // eax
  void *v16; // r8
  int updated; // eax
  __int128 v19; // [rsp+30h] [rbp-10h] BYREF
  struct _PACTYPE *v20; // [rsp+88h] [rbp+48h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp+50h] BYREF

  v3 = (struct _PACTYPE *)*a2;
  v4 = 0;
  Size = *a3;
  v20 = 0;
  hMem = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids);
  if ( PAC_UnMarshal(v3, Size) )
  {
    v19 = 0;
    if ( v3 )
    {
      for ( i = (char *)v3 + 8; i < (char *)v3 + 16 * *(unsigned int *)v3 + 8; i += 16 )
      {
        if ( *(_DWORD *)i == 1 )
        {
          if ( !i )
            break;
          v15 = PAC_UnmarshallValidationInfo(
                  (struct _NETLOGON_VALIDATION_SAM_INFO3 **)&hMem,
                  *((unsigned __int8 **)i + 1),
                  *((_DWORD *)i + 1));
          v10 = v15;
          if ( v15 >= 0 )
          {
            v10 = DigestFilterSids(a1, (struct _NETLOGON_VALIDATION_SAM_INFO3 *)hMem);
            if ( v10 >= 0 )
            {
              updated = PAC_InitAndUpdateGroupsEx(
                          (struct _NETLOGON_VALIDATION_SAM_INFO3 *)hMem,
                          (struct _SAMPR_PSID_ARRAY *)&v19,
                          v16,
                          v3,
                          &v20);
              v10 = updated;
              if ( updated >= 0 )
              {
                v4 = v20;
                Size = PAC_GetSize(v20);
                v3 = v4;
                goto LABEL_18;
              }
              v9 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  68,
                  &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids,
                  (unsigned int)updated);
                v4 = v20;
                goto LABEL_18;
              }
              v4 = v20;
            }
            else
            {
              v9 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v12 = 67;
                goto LABEL_17;
              }
            }
          }
          else
          {
            v9 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                66,
                &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids,
                (unsigned int)v15);
              goto LABEL_18;
            }
          }
          goto LABEL_19;
        }
      }
    }
    v10 = 0;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 65;
LABEL_17:
      WPP_SF_(v9[2], v12, &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids);
LABEL_18:
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_19:
    if ( v3 )
    {
      for ( j = 0; j < *(_DWORD *)v3; ++j )
      {
        v14 = (struct _PACTYPE *)((char *)v3 + Size);
        if ( *((_QWORD *)v3 + 2 * j + 2) > (unsigned __int64)v14 || v3 > v14 )
        {
          v10 = -2146893047;
          goto LABEL_44;
        }
        *((_QWORD *)v3 + 2 * j + 2) = (unsigned int)(*((_DWORD *)v3 + 4 * j + 4) - (_DWORD)v3);
      }
      if ( !v4 )
        goto LABEL_47;
      if ( *a2 != v4 )
      {
        DigestFreeMemory(*a2);
        *a2 = v4;
        v4 = 0;
        *a3 = Size;
      }
LABEL_44:
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 )
    {
      DigestFreeMemory(v4);
LABEL_47:
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = -2146893047;
  }
  if ( hMem )
  {
    DigestFreeMemory(hMem);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && *((char *)v9 + 28) < 0 )
    WPP_SF_d(v9[2], 69, &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids, (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180022bb8  mov     [rsp-38h+arg_0], rbx
0x180022bbd  push    rbp
0x180022bbe  push    rsi
0x180022bbf  push    rdi
0x180022bc0  push    r12
0x180022bc2  push    r13
0x180022bc4  push    r14
0x180022bc6  push    r15
0x180022bc8  mov     rbp, rsp
0x180022bcb  sub     rsp, 40h
0x180022bcf  mov     rsi, [rdx]
0x180022bd2  xor     edi, edi
0x180022bd4  mov     r15d, [r8]
0x180022bd7  mov     r13, r8
0x180022bda  mov     [rbp+arg_8], rdi
0x180022bde  mov     r12, rdx
0x180022be1  mov     [rbp+hMem], rdi
0x180022be5  mov     r14, rcx
0x180022be8  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bef  lea     rbx, WPP_GLOBAL_Control
0x180022bf6  cmp     rcx, rbx
0x180022bf9  jz      short loc_180022C14
0x180022bfb  test    byte ptr [rcx+1Ch], 80h
0x180022bff  jz      short loc_180022C14
0x180022c01  mov     rcx, [rcx+10h]
0x180022c05  lea     edx, [rdi+3Fh]
0x180022c08  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180022c0f  call    WPP_SF_
0x180022c14  mov     edx, r15d; unsigned int
0x180022c17  mov     rcx, rsi; struct _PACTYPE *
0x180022c1a  call    ?PAC_UnMarshal@@YAKPEAU_PACTYPE@@K@Z; PAC_UnMarshal(_PACTYPE *,ulong)
0x180022c1f  test    eax, eax
0x180022c21  jnz     short loc_180022C60
0x180022c23  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c2a  cmp     rcx, rbx
0x180022c2d  jz      short loc_180022C4F
0x180022c2f  test    byte ptr [rcx+1Ch], 1
0x180022c33  jz      short loc_180022C4F
0x180022c35  mov     rcx, [rcx+10h]
0x180022c39  lea     edx, [rax+40h]
0x180022c3c  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180022c43  call    WPP_SF_
0x180022c48  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c4f  mov     ebx, 80090309h
0x180022c54  lea     r14, WPP_GLOBAL_Control
0x180022c5b  jmp     loc_180022E52
0x180022c60  xorps   xmm0, xmm0
0x180022c63  movups  [rbp+var_10], xmm0
0x180022c67  test    rsi, rsi
0x180022c6a  jz      short loc_180022C8D
0x180022c6c  mov     ecx, [rsi]
0x180022c6e  lea     rdx, [rsi+8]
0x180022c72  shl     rcx, 4
0x180022c76  add     rcx, 8
0x180022c7a  add     rcx, rsi
0x180022c7d  jmp     short loc_180022C88
0x180022c7f  cmp     dword ptr [rdx], 1
0x180022c82  jz      short loc_180022D03
0x180022c84  add     rdx, 10h
0x180022c88  cmp     rdx, rcx
0x180022c8b  jb      short loc_180022C7F
0x180022c8d  xor     ebx, ebx
0x180022c8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c96  lea     r14, WPP_GLOBAL_Control
0x180022c9d  cmp     rcx, r14
0x180022ca0  jz      short loc_180022CC2
0x180022ca2  test    byte ptr [rcx+1Ch], 2
0x180022ca6  jz      short loc_180022CC2
0x180022ca8  lea     edx, [rbx+41h]
0x180022cab  mov     rcx, [rcx+10h]
0x180022caf  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180022cb6  call    WPP_SF_
0x180022cbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180022cc2  test    rsi, rsi
0x180022cc5  jz      loc_180022E3E
0x180022ccb  xor     edx, edx
0x180022ccd  cmp     edx, [rsi]
0x180022ccf  jnb     loc_180022E19
0x180022cd5  mov     ecx, edx
0x180022cd7  inc     rcx
0x180022cda  mov     r8d, r15d
0x180022cdd  add     rcx, rcx
0x180022ce0  add     r8, rsi
0x180022ce3  cmp     [rsi+rcx*8], r8
0x180022ce7  ja      loc_180022E12
0x180022ced  cmp     rsi, r8
0x180022cf0  ja      loc_180022E12
0x180022cf6  mov     eax, [rsi+rcx*8]
0x180022cf9  sub     eax, esi
0x180022cfb  mov     [rsi+rcx*8], rax
0x180022cff  inc     edx
0x180022d01  jmp     short loc_180022CCD
0x180022d03  test    rdx, rdx
0x180022d06  jz      short loc_180022C8D
0x180022d08  mov     r8d, [rdx+4]; unsigned int
0x180022d0c  lea     rcx, [rbp+hMem]; struct _NETLOGON_VALIDATION_SAM_INFO3 **
0x180022d10  mov     rdx, [rdx+8]; unsigned __int8 *
0x180022d14  call    ?PAC_UnmarshallValidationInfo@@YAJPEAPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAEK@Z; PAC_UnmarshallValidationInfo(_NETLOGON_VALIDATION_SAM_INFO3 * *,uchar *,ulong)
0x180022d19  mov     ebx, eax
0x180022d1b  test    eax, eax
0x180022d1d  jns     short loc_180022D55
0x180022d1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d26  lea     r14, WPP_GLOBAL_Control
0x180022d2d  cmp     rcx, r14
0x180022d30  jz      short loc_180022CC2
0x180022d32  test    byte ptr [rcx+1Ch], 1
0x180022d36  jz      short loc_180022CC2
0x180022d38  mov     rcx, [rcx+10h]
0x180022d3c  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180022d43  mov     edx, 42h ; 'B'
0x180022d48  mov     r9d, eax
0x180022d4b  call    WPP_SF_d
0x180022d50  jmp     loc_180022CBB
0x180022d55  mov     rdx, [rbp+hMem]; struct _NETLOGON_VALIDATION_SAM_INFO3 *
0x180022d59  mov     rcx, r14; struct _DIGEST_PARAMETER *
0x180022d5c  call    ?DigestFilterSids@@YAJPEAU_DIGEST_PARAMETER@@PEAU_NETLOGON_VALIDATION_SAM_INFO3@@@Z; DigestFilterSids(_DIGEST_PARAMETER *,_NETLOGON_VALIDATION_SAM_INFO3 *)
0x180022d61  mov     ebx, eax
0x180022d63  test    eax, eax
0x180022d65  jns     short loc_180022D92
0x180022d67  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d6e  lea     r14, WPP_GLOBAL_Control
0x180022d75  cmp     rcx, r14
0x180022d78  jz      loc_180022CC2
0x180022d7e  test    byte ptr [rcx+1Ch], 1
0x180022d82  jz      loc_180022CC2
0x180022d88  mov     edx, 43h ; 'C'
0x180022d8d  jmp     loc_180022CAB
0x180022d92  mov     rcx, [rbp+hMem]; struct _NETLOGON_VALIDATION_SAM_INFO3 *
0x180022d96  lea     rax, [rbp+arg_8]
0x180022d9a  mov     r9, rsi; struct _PACTYPE *
0x180022d9d  mov     [rsp+40h+var_20], rax; struct _PACTYPE **
0x180022da2  lea     rdx, [rbp+var_10]; struct _SAMPR_PSID_ARRAY *
0x180022da6  call    ?PAC_InitAndUpdateGroupsEx@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAU_SAMPR_PSID_ARRAY@@PEAXPEAU_PACTYPE@@PEAPEAU3@@Z; PAC_InitAndUpdateGroupsEx(_NETLOGON_VALIDATION_SAM_INFO3 *,_SAMPR_PSID_ARRAY *,void *,_PACTYPE *,_PACTYPE * *)
0x180022dab  mov     ebx, eax
0x180022dad  test    eax, eax
0x180022daf  jns     short loc_180022DF4
0x180022db1  mov     rcx, cs:WPP_GLOBAL_Control
0x180022db8  lea     r14, WPP_GLOBAL_Control
0x180022dbf  cmp     rcx, r14
0x180022dc2  jz      short loc_180022DEB
0x180022dc4  test    byte ptr [rcx+1Ch], 1
0x180022dc8  jz      short loc_180022DEB
0x180022dca  mov     rcx, [rcx+10h]
0x180022dce  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180022dd5  mov     edx, 44h ; 'D'
0x180022dda  mov     r9d, eax
0x180022ddd  call    WPP_SF_d
0x180022de2  mov     rdi, [rbp+arg_8]
0x180022de6  jmp     loc_180022CBB
0x180022deb  mov     rdi, [rbp+arg_8]
0x180022def  jmp     loc_180022CC2
0x180022df4  mov     rdi, [rbp+arg_8]
0x180022df8  mov     rcx, rdi; struct _PACTYPE *
0x180022dfb  call    ?PAC_GetSize@@YAKPEAU_PACTYPE@@@Z; PAC_GetSize(_PACTYPE *)
0x180022e00  mov     r15d, eax
0x180022e03  lea     r14, WPP_GLOBAL_Control
0x180022e0a  mov     rsi, rdi
0x180022e0d  jmp     loc_180022CBB
0x180022e12  mov     ebx, 80090309h
0x180022e17  jmp     short loc_180022E37
0x180022e19  test    rdi, rdi
0x180022e1c  jz      short loc_180022E4B
0x180022e1e  cmp     [r12], rdi
0x180022e22  jz      short loc_180022E37
0x180022e24  mov     rcx, [r12]; hMem
0x180022e28  call    DigestFreeMemory
0x180022e2d  mov     [r12], rdi
0x180022e31  xor     edi, edi
0x180022e33  mov     [r13+0], r15d
0x180022e37  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e3e  test    rdi, rdi
0x180022e41  jz      short loc_180022E52
0x180022e43  mov     rcx, rdi; hMem
0x180022e46  call    DigestFreeMemory
0x180022e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e52  mov     rax, [rbp+hMem]
0x180022e56  test    rax, rax
0x180022e59  jz      short loc_180022E6A
0x180022e5b  mov     rcx, rax; hMem
0x180022e5e  call    DigestFreeMemory
0x180022e63  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e6a  cmp     rcx, r14
0x180022e6d  jz      short loc_180022E8D
0x180022e6f  test    byte ptr [rcx+1Ch], 80h
0x180022e73  jz      short loc_180022E8D
0x180022e75  mov     rcx, [rcx+10h]
0x180022e79  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180022e80  mov     edx, 45h ; 'E'
0x180022e85  mov     r9d, ebx
0x180022e88  call    WPP_SF_d
0x180022e8d  mov     eax, ebx
0x180022e8f  mov     rbx, [rsp+40h+arg_0]
0x180022e97  add     rsp, 40h
0x180022e9b  pop     r15
0x180022e9d  pop     r14
0x180022e9f  pop     r13
0x180022ea1  pop     r12
0x180022ea3  pop     rdi
0x180022ea4  pop     rsi
0x180022ea5  pop     rbp
0x180022ea6  retn
```
