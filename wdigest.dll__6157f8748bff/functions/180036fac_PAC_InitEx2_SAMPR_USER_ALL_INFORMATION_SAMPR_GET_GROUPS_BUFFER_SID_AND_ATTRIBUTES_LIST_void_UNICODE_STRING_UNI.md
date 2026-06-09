# PAC_InitEx2(_SAMPR_USER_ALL_INFORMATION *,_SAMPR_GET_GROUPS_BUFFER *,_SID_AND_ATTRIBUTES_LIST *,void *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,ulong,_PAC_INFO_BUFFER * *,_LARGE_INTEGER *,_LARGE_INTEGER *,_LSA_LAST_INTER_LOGON_INFO *,_PACTYPE * *)

- ea: `0x180036fac`
- end: `0x1800370b2`
- name: `?PAC_InitEx2@@YAJPEAU_SAMPR_USER_ALL_INFORMATION@@PEAU_SAMPR_GET_GROUPS_BUFFER@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAXPEAU_UNICODE_STRING@@4KKKPEAPEAU_PAC_INFO_BUFFER@@PEAT_LARGE_INTEGER@@6PEAU_LSA_LAST_INTER_LOGON_INFO@@PEAPEAU_PACTYPE@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct _SAMPR_USER_ALL_INFORMATION *, struct _SAMPR_GET_GROUPS_BUFFER *, struct _SID_AND_ATTRIBUTES_LIST *, void *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, size_t Size, unsigned int, unsigned int, struct _PAC_INFO_BUFFER **, union _LARGE_INTEGER *, union _LARGE_INTEGER *, struct _LSA_LAST_INTER_LOGON_INFO *, struct _PACTYPE **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18002357c`

## callees

- `0x180009770`
- `0x180013304`
- `0x180023f80`
- `0x180036fac`
- `0x1800370b8`
- `0x1800377bc`

## pseudocode

```c
__int64 __fastcall PAC_InitEx2(
        struct _SAMPR_USER_ALL_INFORMATION *a1,
        struct _SAMPR_GET_GROUPS_BUFFER *a2,
        const void **a3,
        void *a4,
        struct _UNICODE_STRING *a5,
        struct _UNICODE_STRING *a6,
        size_t Size,
        unsigned int a8,
        unsigned int a9,
        struct _PAC_INFO_BUFFER **a10,
        union _LARGE_INTEGER *a11,
        union _LARGE_INTEGER *a12,
        struct _LSA_LAST_INTER_LOGON_INFO *a13,
        struct _PACTYPE **a14)
{
  struct _PACTYPE **v14; // r14
  int v15; // ebx
  size_t v16; // rsi
  unsigned int v17; // eax
  size_t v18; // rcx
  size_t v19; // rbp
  _DWORD *v20; // rax
  _DWORD *v21; // rdi
  void *v22; // rdx
  void *v23; // rcx
  struct _UNICODE_STRING *v25; // [rsp+20h] [rbp-68h]
  struct _UNICODE_STRING *v26; // [rsp+28h] [rbp-60h]
  unsigned __int8 v27; // [rsp+30h] [rbp-58h]
  unsigned __int8 v28; // [rsp+38h] [rbp-50h]
  union _LARGE_INTEGER *v29; // [rsp+40h] [rbp-48h]
  union _LARGE_INTEGER *v30; // [rsp+48h] [rbp-40h]
  struct _LSA_LAST_INTER_LOGON_INFO *v31; // [rsp+50h] [rbp-38h]
  void *Src; // [rsp+98h] [rbp+10h] BYREF

  v14 = a14;
  v25 = a5;
  Src = 0;
  LODWORD(Size) = 0;
  *a14 = 0;
  v15 = PAC_MarshallValidationInfo(
          a1,
          a2,
          a3,
          a4,
          v25,
          v26,
          v27,
          v28,
          v29,
          v30,
          v31,
          (unsigned __int8 **)&Src,
          (unsigned int *)&Size);
  if ( v15 >= 0 )
  {
    v16 = (unsigned int)Size;
    v17 = (Size + 7) & 0xFFFFFFF8;
    v18 = v17 + 24;
    if ( (unsigned int)v18 >= v17 )
    {
      if ( (unsigned int)v18 < 0xFFFF )
      {
        v19 = (unsigned int)v18;
        v20 = MIDL_user_allocate(v18);
        v21 = v20;
        if ( v20 )
        {
          v15 = 0;
          memset_0(v20, 0, v19);
          v22 = Src;
          *(_QWORD *)v21 = 1;
          v23 = (void *)(((unsigned __int64)v21 + 31) & 0xFFFFFFFFFFFFFFF8uLL);
          v21[2] = 1;
          *((_QWORD *)v21 + 2) = v23;
          v21[3] = v16;
          memcpy_0(v23, v22, v16);
          *v14 = (struct _PACTYPE *)v21;
        }
        else
        {
          v15 = -1073741670;
        }
      }
      else
      {
        v15 = -1073741637;
      }
    }
    else
    {
      v15 = -1073741675;
    }
  }
  DigestFreeMemory(Src);
  DigestFreeMemory(0);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180036fac  mov     r11, rsp
0x180036faf  mov     [r11+8], rbx
0x180036fb3  mov     [r11+18h], rbp
0x180036fb7  mov     [r11+10h], rdx
0x180036fbb  push    rsi
0x180036fbc  push    rdi
0x180036fbd  push    r14
0x180036fbf  sub     rsp, 70h
0x180036fc3  mov     r14, [rsp+88h+arg_68]
0x180036fcb  lea     rax, [r11+38h]
0x180036fcf  mov     [r11-28h], rax
0x180036fd3  lea     rax, [r11+10h]
0x180036fd7  mov     [r11-30h], rax
0x180036fdb  mov     rax, [rsp+88h+arg_20]
0x180036fe3  mov     [r11-68h], rax
0x180036fe7  mov     qword ptr [r11+10h], 0
0x180036fef  mov     dword ptr [r11+38h], 0
0x180036ff7  mov     qword ptr [r14], 0
0x180036ffe  call    ?PAC_MarshallValidationInfo@@YAJPEAU_SAMPR_USER_ALL_INFORMATION@@PEAU_SAMPR_GET_GROUPS_BUFFER@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAXPEAU_UNICODE_STRING@@4EEPEAT_LARGE_INTEGER@@5PEAU_LSA_LAST_INTER_LOGON_INFO@@PEAPEAEPEAK@Z; PAC_MarshallValidationInfo(_SAMPR_USER_ALL_INFORMATION *,_SAMPR_GET_GROUPS_BUFFER *,_SID_AND_ATTRIBUTES_LIST *,void *,_UNICODE_STRING *,_UNICODE_STRING *,uchar,uchar,_LARGE_INTEGER *,_LARGE_INTEGER *,_LSA_LAST_INTER_LOGON_INFO *,uchar * *,ulong *)
0x180037003  mov     ebx, eax
0x180037005  test    eax, eax
0x180037007  js      short loc_180037087
0x180037009  mov     esi, dword ptr [rsp+88h+Size]
0x180037010  lea     eax, [rsi+7]
0x180037013  and     eax, 0FFFFFFF8h
0x180037016  lea     ecx, [rax+18h]; size
0x180037019  cmp     ecx, eax
0x18003701b  jnb     short loc_180037024
0x18003701d  mov     ebx, 0C0000095h
0x180037022  jmp     short loc_180037087
0x180037024  cmp     ecx, 0FFFFh
0x18003702a  jb      short loc_180037033
0x18003702c  mov     ebx, 0C00000BBh
0x180037031  jmp     short loc_180037087
0x180037033  mov     ebp, ecx
0x180037035  call    MIDL_user_allocate
0x18003703a  mov     rdi, rax
0x18003703d  test    rax, rax
0x180037040  jnz     short loc_180037049
0x180037042  mov     ebx, 0C000009Ah
0x180037047  jmp     short loc_180037087
0x180037049  mov     r8, rbp; Size
0x18003704c  xor     edx, edx; Val
0x18003704e  mov     rcx, rdi; void *
0x180037051  xor     ebx, ebx
0x180037053  call    memset_0
0x180037058  mov     rdx, [rsp+88h+Src]; Src
0x180037060  lea     eax, [rbx+1]
0x180037063  mov     qword ptr [rdi], 1
0x18003706a  lea     rcx, [rdi+1Fh]
0x18003706e  and     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180037072  mov     [rdi+8], eax
0x180037075  mov     r8, rsi; Size
0x180037078  mov     [rdi+10h], rcx
0x18003707c  mov     [rdi+0Ch], esi
0x18003707f  call    memcpy_0
0x180037084  mov     [r14], rdi
0x180037087  mov     rcx, [rsp+88h+Src]; hMem
0x18003708f  call    DigestFreeMemory
0x180037094  xor     ecx, ecx; hMem
0x180037096  call    DigestFreeMemory
0x18003709b  lea     r11, [rsp+88h+var_18]
0x1800370a0  mov     eax, ebx
0x1800370a2  mov     rbx, [r11+20h]
0x1800370a6  mov     rbp, [r11+30h]
0x1800370aa  mov     rsp, r11
0x1800370ad  pop     r14
0x1800370af  pop     rdi
0x1800370b0  pop     rsi
0x1800370b1  retn
```
