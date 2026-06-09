# PAC_InitAndUpdateGroupsEx(_NETLOGON_VALIDATION_SAM_INFO3 *,_SAMPR_PSID_ARRAY *,void *,_PACTYPE *,_PACTYPE * *)

- ea: `0x180036ddc`
- end: `0x180036fa6`
- name: `?PAC_InitAndUpdateGroupsEx@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAU_SAMPR_PSID_ARRAY@@PEAXPEAU_PACTYPE@@PEAPEAU3@@Z`
- size: `458`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO3 *, struct _SAMPR_PSID_ARRAY *, void *, struct _PACTYPE *, struct _PACTYPE **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180022bb8`

## callees

- `0x180009770`
- `0x180013304`
- `0x180023f80`
- `0x180036ddc`
- `0x1800372bc`
- `0x1800377bc`

## pseudocode

```c
__int64 __fastcall PAC_InitAndUpdateGroupsEx(
        struct _NETLOGON_VALIDATION_SAM_INFO3 *a1,
        struct _SAMPR_PSID_ARRAY *a2,
        void *a3,
        struct _PACTYPE *a4,
        struct _PACTYPE **a5)
{
  struct _PACTYPE **v5; // r12
  int v7; // ebx
  size_t v8; // r14
  unsigned int v9; // ecx
  unsigned int v10; // r13d
  unsigned int v11; // edx
  __int64 v12; // rbx
  unsigned int v13; // eax
  unsigned int v14; // ebp
  size_t v15; // rbp
  unsigned int *v16; // rax
  unsigned int *v17; // rsi
  void *v18; // rdx
  void *v19; // rbx
  unsigned int v20; // ebp
  void *i; // r14
  unsigned int v22; // eax
  __int64 v23; // rbx
  void *Src; // [rsp+30h] [rbp-38h] BYREF
  unsigned int Size; // [rsp+80h] [rbp+18h] BYREF
  int Size_4; // [rsp+84h] [rbp+1Ch]

  Size_4 = HIDWORD(a3);
  v5 = a5;
  Src = 0;
  Size = 0;
  *a5 = 0;
  v7 = PAC_ReMarshallValidationInfoWithGroups(a1, a2, a3, (unsigned __int8 **)&Src, &Size);
  if ( v7 >= 0 )
  {
    v8 = Size;
    if ( Size >= 0xFFFF )
      goto LABEL_3;
    v9 = (Size + 7) & 0xFFFFFFF8;
    v10 = 1;
    v11 = 0;
    v12 = 1;
    while ( v11 < *(_DWORD *)a4 )
    {
      if ( *((_DWORD *)a4 + 4 * v11 + 2) != 1 )
      {
        v13 = *((_DWORD *)a4 + 4 * v11 + 3);
        if ( v13 >= 0xFFFF )
          goto LABEL_3;
        if ( v9 + ((v13 + 7) & 0xFFFFFFF8) < v9 )
        {
          v7 = -1073741675;
          goto LABEL_20;
        }
        v9 += (v13 + 7) & 0xFFFFFFF8;
        v12 = (unsigned int)(v12 + 1);
      }
      ++v11;
    }
    v14 = v9 + 16 * (v12 - 1) + 24;
    if ( v14 >= 0xFFFF )
    {
LABEL_3:
      v7 = -1073741637;
    }
    else
    {
      v15 = (v14 + 7) & 0xFFFFFFF8;
      v16 = (unsigned int *)MIDL_user_allocate(v15);
      v17 = v16;
      if ( v16 )
      {
        memset_0(v16, 0, v15);
        v18 = Src;
        *v17 = v12;
        v17[2] = 1;
        v17[3] = v8;
        v19 = (void *)(((unsigned __int64)&v17[4 * v12 + 3] + 3) & 0xFFFFFFFFFFFFFFF8uLL);
        *((_QWORD *)v17 + 2) = v19;
        memcpy_0(v19, v18, v8);
        v20 = 0;
        for ( i = (void *)(((unsigned __int64)v19 + v17[3] + 7) & 0xFFFFFFFFFFFFFFF8uLL); v20 < *(_DWORD *)a4; ++v20 )
        {
          v22 = *((_DWORD *)a4 + 4 * v20 + 2);
          if ( v22 != 1 )
          {
            v23 = 2LL * v10;
            v17[2 * v23 + 2] = v22;
            v17[2 * v23 + 3] = *((_DWORD *)a4 + 4 * v20 + 3);
            *(_QWORD *)&v17[2 * v23 + 4] = i;
            memcpy_0(i, *((const void **)a4 + 2 * v20 + 2), *((unsigned int *)a4 + 4 * v20 + 3));
            i = (void *)(((unsigned __int64)i + v17[4 * v10++ + 3] + 7) & 0xFFFFFFFFFFFFFFF8uLL);
          }
        }
        *v5 = (struct _PACTYPE *)v17;
        v7 = 0;
      }
      else
      {
        v7 = -1073741670;
      }
    }
  }
LABEL_20:
  if ( Src )
    DigestFreeMemory(Src);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180036ddc  mov     r11, rsp
0x180036ddf  mov     [r11+8], rbx
0x180036de3  mov     [r11+10h], rbp
0x180036de7  mov     [r11+18h], r8
0x180036deb  push    rsi
0x180036dec  push    rdi
0x180036ded  push    r12
0x180036def  push    r13
0x180036df1  push    r14
0x180036df3  sub     rsp, 40h
0x180036df7  mov     r12, [rsp+68h+arg_20]
0x180036dff  lea     rax, [r11+18h]
0x180036e03  mov     rdi, r9
0x180036e06  mov     qword ptr [r11-38h], 0
0x180036e0e  lea     r9, [r11-38h]; unsigned __int8 **
0x180036e12  mov     dword ptr [r11+18h], 0
0x180036e1a  mov     [r11-48h], rax
0x180036e1e  mov     qword ptr [r12], 0
0x180036e26  call    ?PAC_ReMarshallValidationInfoWithGroups@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAU_SAMPR_PSID_ARRAY@@PEAXPEAPEAEPEAK@Z; PAC_ReMarshallValidationInfoWithGroups(_NETLOGON_VALIDATION_SAM_INFO3 *,_SAMPR_PSID_ARRAY *,void *,uchar * *,ulong *)
0x180036e2b  mov     ebx, eax
0x180036e2d  test    eax, eax
0x180036e2f  js      loc_180036F7B
0x180036e35  mov     r14d, dword ptr [rsp+68h+Size]
0x180036e3d  mov     r9d, 0FFFFh
0x180036e43  cmp     r14d, r9d
0x180036e46  jb      short loc_180036E52
0x180036e48  mov     ebx, 0C00000BBh
0x180036e4d  jmp     loc_180036F7B
0x180036e52  lea     ecx, [r14+7]
0x180036e56  mov     r10d, 0FFFFFFF8h
0x180036e5c  and     ecx, r10d
0x180036e5f  mov     r13d, 1
0x180036e65  xor     edx, edx
0x180036e67  mov     ebx, r13d
0x180036e6a  cmp     edx, [rdi]
0x180036e6c  jnb     short loc_180036EA7
0x180036e6e  mov     eax, edx
0x180036e70  add     rax, rax
0x180036e73  cmp     [rdi+rax*8+8], r13d
0x180036e78  jz      short loc_180036E98
0x180036e7a  mov     eax, [rdi+rax*8+0Ch]
0x180036e7e  cmp     eax, r9d
0x180036e81  jnb     short loc_180036E48
0x180036e83  lea     r8d, [rax+7]
0x180036e87  and     r8d, r10d
0x180036e8a  add     r8d, ecx
0x180036e8d  cmp     r8d, ecx
0x180036e90  jb      short loc_180036E9D
0x180036e92  mov     ecx, r8d
0x180036e95  add     ebx, r13d
0x180036e98  add     edx, r13d
0x180036e9b  jmp     short loc_180036E6A
0x180036e9d  mov     ebx, 0C0000095h
0x180036ea2  jmp     loc_180036F7B
0x180036ea7  lea     ebp, [rbx-1]
0x180036eaa  shl     ebp, 4
0x180036ead  add     ebp, 18h
0x180036eb0  add     ebp, ecx
0x180036eb2  cmp     ebp, r9d
0x180036eb5  jnb     short loc_180036E48
0x180036eb7  add     ebp, 7
0x180036eba  and     rbp, r10
0x180036ebd  mov     rcx, rbp; size
0x180036ec0  call    MIDL_user_allocate
0x180036ec5  mov     rsi, rax
0x180036ec8  test    rax, rax
0x180036ecb  jnz     short loc_180036ED7
0x180036ecd  mov     ebx, 0C000009Ah
0x180036ed2  jmp     loc_180036F7B
0x180036ed7  mov     r8, rbp; Size
0x180036eda  xor     edx, edx; Val
0x180036edc  mov     rcx, rsi; void *
0x180036edf  call    memset_0
0x180036ee4  mov     rdx, [rsp+68h+Src]; Src
0x180036ee9  mov     r8, r14; Size
0x180036eec  mov     [rsi], ebx
0x180036eee  shl     rbx, 4
0x180036ef2  add     rbx, 0Fh
0x180036ef6  mov     [rsi+8], r13d
0x180036efa  add     rbx, rsi
0x180036efd  mov     [rsi+0Ch], r14d
0x180036f01  and     rbx, 0FFFFFFFFFFFFFFF8h
0x180036f05  mov     rcx, rbx; void *
0x180036f08  mov     [rsi+10h], rbx
0x180036f0c  call    memcpy_0
0x180036f11  mov     r14d, [rsi+0Ch]
0x180036f15  xor     ebp, ebp
0x180036f17  add     r14, 7
0x180036f1b  add     r14, rbx
0x180036f1e  and     r14, 0FFFFFFFFFFFFFFF8h
0x180036f22  cmp     [rdi], ebp
0x180036f24  jbe     short loc_180036F75
0x180036f26  mov     edx, ebp
0x180036f28  add     rdx, rdx
0x180036f2b  mov     eax, [rdi+rdx*8+8]
0x180036f2f  cmp     eax, 1
0x180036f32  jz      short loc_180036F6F
0x180036f34  mov     ebx, r13d
0x180036f37  mov     rcx, r14; void *
0x180036f3a  add     rbx, rbx
0x180036f3d  mov     [rsi+rbx*8+8], eax
0x180036f41  mov     eax, [rdi+rdx*8+0Ch]
0x180036f45  mov     [rsi+rbx*8+0Ch], eax
0x180036f49  mov     [rsi+rbx*8+10h], r14
0x180036f4e  mov     r8d, [rdi+rdx*8+0Ch]; Size
0x180036f53  mov     rdx, [rdi+rdx*8+10h]; Src
0x180036f58  call    memcpy_0
0x180036f5d  mov     eax, [rsi+rbx*8+0Ch]
0x180036f61  add     r14, 7
0x180036f65  add     r14, rax
0x180036f68  and     r14, 0FFFFFFFFFFFFFFF8h
0x180036f6c  inc     r13d
0x180036f6f  inc     ebp
0x180036f71  cmp     ebp, [rdi]
0x180036f73  jb      short loc_180036F26
0x180036f75  mov     [r12], rsi
0x180036f79  xor     ebx, ebx
0x180036f7b  cmp     [rsp+68h+Src], 0
0x180036f81  jz      short loc_180036F8D
0x180036f83  mov     rcx, [rsp+68h+Src]; hMem
0x180036f88  call    DigestFreeMemory
0x180036f8d  mov     rbp, [rsp+68h+arg_8]
0x180036f92  mov     eax, ebx
0x180036f94  mov     rbx, [rsp+68h+arg_0]
0x180036f99  add     rsp, 40h
0x180036f9d  pop     r14
0x180036f9f  pop     r13
0x180036fa1  pop     r12
0x180036fa3  pop     rdi
0x180036fa4  pop     rsi
0x180036fa5  retn
```
