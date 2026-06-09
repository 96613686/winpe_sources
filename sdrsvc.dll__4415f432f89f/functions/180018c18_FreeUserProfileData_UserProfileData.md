# FreeUserProfileData(_UserProfileData *)

- ea: `0x180018c18`
- end: `0x180018d32`
- name: `?FreeUserProfileData@@YAXPEAU_UserProfileData@@@Z`
- size: `282`
- prototype: `void __fastcall(struct _UserProfileData *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800106f4`
- `0x1800190bc`

## callees

- `0x180018c18`
- `0x18002170a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ca8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018cda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018d14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ca8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018cda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018d14`

## pseudocode

```c
void __fastcall FreeUserProfileData(struct _UserProfileData *a1)
{
  LPVOID *v2; // rdi
  LPVOID *v3; // rdi
  LPVOID *v4; // rdi
  LPVOID *v5; // rdi
  unsigned int i; // edi
  __int64 v7; // rsi
  LPVOID *v8; // r14
  LPVOID *v9; // rsi

  if ( a1 )
  {
    CoTaskMemFree(*(LPVOID *)a1);
    v2 = (LPVOID *)((char *)a1 + 16);
    *(_QWORD *)a1 = 0;
    if ( a1 != (struct _UserProfileData *)-16LL && *v2 )
    {
      CoTaskMemFree(*v2);
      *v2 = 0;
    }
    v3 = (LPVOID *)((char *)a1 + 24);
    if ( a1 != (struct _UserProfileData *)-24LL && *v3 )
    {
      CoTaskMemFree(*v3);
      *v3 = 0;
    }
    v4 = (LPVOID *)((char *)a1 + 32);
    if ( a1 != (struct _UserProfileData *)-32LL && *v4 )
    {
      CoTaskMemFree(*v4);
      *v4 = 0;
    }
    v5 = (LPVOID *)((char *)a1 + 40);
    if ( a1 != (struct _UserProfileData *)-40LL && *v5 )
    {
      CoTaskMemFree(*v5);
      *v5 = 0;
    }
    if ( *((_QWORD *)a1 + 6) )
    {
      for ( i = 0; i < *((_DWORD *)a1 + 14); ++i )
      {
        v7 = 16LL * i;
        v8 = (LPVOID *)(v7 + *((_QWORD *)a1 + 6));
        if ( v8 && *v8 )
        {
          CoTaskMemFree(*v8);
          *v8 = 0;
        }
        v9 = (LPVOID *)(*((_QWORD *)a1 + 6) + 8LL + v7);
        if ( v9 )
        {
          if ( *v9 )
          {
            CoTaskMemFree(*v9);
            *v9 = 0;
          }
        }
      }
      CoTaskMemFree(*((LPVOID *)a1 + 6));
    }
    memset_0(a1, 0, 0x40u);
  }
}

```

## disassembly

```asm
0x180018c18  test    rcx, rcx
0x180018c1b  jz      locret_180018D31
0x180018c21  push    rbx
0x180018c22  push    rsi
0x180018c23  push    rdi
0x180018c24  push    r14
0x180018c26  sub     rsp, 28h
0x180018c2a  mov     rbx, rcx
0x180018c2d  mov     rcx, [rcx]; pv
0x180018c30  call    cs:__imp_CoTaskMemFree
0x180018c36  lea     rdi, [rbx+10h]
0x180018c3a  mov     qword ptr [rbx], 0
0x180018c41  test    rdi, rdi
0x180018c44  jz      short loc_180018C5B
0x180018c46  mov     rcx, [rdi]; pv
0x180018c49  test    rcx, rcx
0x180018c4c  jz      short loc_180018C5B
0x180018c4e  call    cs:__imp_CoTaskMemFree
0x180018c54  mov     qword ptr [rdi], 0
0x180018c5b  lea     rdi, [rbx+18h]
0x180018c5f  test    rdi, rdi
0x180018c62  jz      short loc_180018C79
0x180018c64  mov     rcx, [rdi]; pv
0x180018c67  test    rcx, rcx
0x180018c6a  jz      short loc_180018C79
0x180018c6c  call    cs:__imp_CoTaskMemFree
0x180018c72  mov     qword ptr [rdi], 0
0x180018c79  lea     rdi, [rbx+20h]
0x180018c7d  test    rdi, rdi
0x180018c80  jz      short loc_180018C97
0x180018c82  mov     rcx, [rdi]; pv
0x180018c85  test    rcx, rcx
0x180018c88  jz      short loc_180018C97
0x180018c8a  call    cs:__imp_CoTaskMemFree
0x180018c90  mov     qword ptr [rdi], 0
0x180018c97  lea     rdi, [rbx+28h]
0x180018c9b  test    rdi, rdi
0x180018c9e  jz      short loc_180018CB5
0x180018ca0  mov     rcx, [rdi]; pv
0x180018ca3  test    rcx, rcx
0x180018ca6  jz      short loc_180018CB5
0x180018ca8  call    cs:__imp_CoTaskMemFree
0x180018cae  mov     qword ptr [rdi], 0
0x180018cb5  cmp     qword ptr [rbx+30h], 0
0x180018cba  jz      short loc_180018D1A
0x180018cbc  xor     edi, edi
0x180018cbe  cmp     [rbx+38h], edi
0x180018cc1  jbe     short loc_180018D10
0x180018cc3  mov     r14, [rbx+30h]
0x180018cc7  mov     esi, edi
0x180018cc9  shl     rsi, 4
0x180018ccd  add     r14, rsi
0x180018cd0  jz      short loc_180018CE7
0x180018cd2  mov     rcx, [r14]; pv
0x180018cd5  test    rcx, rcx
0x180018cd8  jz      short loc_180018CE7
0x180018cda  call    cs:__imp_CoTaskMemFree
0x180018ce0  mov     qword ptr [r14], 0
0x180018ce7  mov     rax, [rbx+30h]
0x180018ceb  add     rax, 8
0x180018cef  add     rsi, rax
0x180018cf2  jz      short loc_180018D09
0x180018cf4  mov     rcx, [rsi]; pv
0x180018cf7  test    rcx, rcx
0x180018cfa  jz      short loc_180018D09
0x180018cfc  call    cs:__imp_CoTaskMemFree
0x180018d02  mov     qword ptr [rsi], 0
0x180018d09  inc     edi
0x180018d0b  cmp     edi, [rbx+38h]
0x180018d0e  jb      short loc_180018CC3
0x180018d10  mov     rcx, [rbx+30h]; pv
0x180018d14  call    cs:__imp_CoTaskMemFree
0x180018d1a  xor     edx, edx; Val
0x180018d1c  mov     rcx, rbx; void *
0x180018d1f  lea     r8d, [rdx+40h]; Size
0x180018d23  call    memset_0
0x180018d28  add     rsp, 28h
0x180018d2c  pop     r14
0x180018d2e  pop     rdi
0x180018d2f  pop     rsi
0x180018d30  pop     rbx
0x180018d31  retn
```
