# CSrDrvWuHelper::_GetBootVolumeProp(_SPP_GROUP_PROP const *,_SPP_BOOT_VOLUME_PROP *,int *)

- ea: `0x18000c258`
- end: `0x18000c462`
- name: `?_GetBootVolumeProp@CSrDrvWuHelper@@CAJPEBU_SPP_GROUP_PROP@@PEAU_SPP_BOOT_VOLUME_PROP@@PEAH@Z`
- size: `522`
- prototype: `__int64 __fastcall(const struct _SPP_GROUP_PROP *, struct _SPP_BOOT_VOLUME_PROP *, int *, unsigned __int16)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a790`
- `0x18000b3b0`
- `0x18000ca98`

## callees

- `0x180003ce0`
- `0x18000c258`
- `0x18000d348`
- `0x18000d43c`
- `0x180014f38`
- `0x180015760`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000c3b7`
- `msvcrt!_wcsicmp` at `0x18000c3b7`

## pseudocode

```c
__int64 __fastcall CSrDrvWuHelper::_GetBootVolumeProp(
        const struct _SPP_GROUP_PROP *a1,
        struct _SPP_BOOT_VOLUME_PROP *a2,
        int *a3,
        unsigned __int16 a4)
{
  unsigned int v7; // r14d
  __int16 v8; // ax
  __int64 v9; // rcx
  struct _SPP_BOOT_VOLUME_PROP *v10; // rax
  const unsigned __int16 *v11; // rdx
  unsigned __int64 v12; // rax
  bool v13; // cf
  wchar_t *v14; // rdx
  unsigned int v15; // r15d
  __int64 v16; // rsi
  __int64 v17; // rdi
  int v18; // eax
  __int128 v19; // xmm0
  unsigned int v20; // ebx
  wchar_t *String2; // [rsp+20h] [rbp-58h] BYREF
  __int64 v23; // [rsp+28h] [rbp-50h]
  int v24; // [rsp+30h] [rbp-48h] BYREF
  __int16 i; // [rsp+34h] [rbp-44h]
  __int16 v26; // [rsp+36h] [rbp-42h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v24, "CSrDrvWuHelper::_GetBootVolumeProp", 0x35Cu, a4);
  v7 = 0;
  String2 = (wchar_t *)qword_18001A620;
  v8 = 864;
  v23 = 0;
  if ( !a1 )
    goto LABEL_23;
  i = 864;
  v8 = 865;
  if ( !a2 )
    goto LABEL_23;
  i = 865;
  v8 = 866;
  if ( !a3 )
    goto LABEL_23;
  i = 866;
  v9 = 80;
  v10 = a2;
  v24 = 0;
  do
  {
    *(_BYTE *)v10 = 0;
    v10 = (struct _SPP_BOOT_VOLUME_PROP *)((char *)v10 + 1);
    --v9;
  }
  while ( v9 );
  v11 = (const unsigned __int16 *)*((_QWORD *)a1 + 7);
  v12 = -1;
  *a3 = 0;
  do
    ++v12;
  while ( v11[v12] );
  v13 = v12 < 3;
  v8 = 871;
  if ( v13 )
    goto LABEL_23;
  v24 = 0;
  i = 871;
  v24 = CBsString::Append((CBsString *)&String2, v11);
  v8 = 873;
  if ( v24 < 0 )
  {
LABEL_24:
    v26 = v8;
    goto LABEL_25;
  }
  i = 873;
  v8 = 874;
  if ( HIDWORD(v23) < 3 )
  {
LABEL_23:
    v24 = -2147024809;
    goto LABEL_24;
  }
  v14 = String2;
  LODWORD(v23) = 3;
  String2[3] = 0;
  v15 = 0;
  v24 = 0;
  for ( i = 874; v15 < *((_DWORD *)a1 + 20); v7 = 0 )
  {
    v16 = *((_QWORD *)a1 + 11);
    v17 = 56LL * v15;
    if ( *(_DWORD *)(v17 + v16 + 32) )
    {
      while ( 1 )
      {
        v18 = _wcsicmp(*(const wchar_t **)(*(_QWORD *)(v17 + v16 + 40) + 8LL * v7), v14);
        v14 = String2;
        if ( !v18 )
          break;
        if ( ++v7 >= *(_DWORD *)(v17 + v16 + 32) )
          goto LABEL_20;
      }
      v19 = *(_OWORD *)(v17 + v16);
      *a3 = 1;
      *(_OWORD *)((char *)a2 + 24) = v19;
      *(_OWORD *)((char *)a2 + 40) = *(_OWORD *)(v17 + v16 + 16);
      *(_OWORD *)((char *)a2 + 56) = *(_OWORD *)(v17 + v16 + 32);
      *((_QWORD *)a2 + 9) = *(_QWORD *)(v17 + v16 + 48);
      *((_QWORD *)a2 + 2) = *((_QWORD *)a1 + 7);
      *(_OWORD *)a2 = *(_OWORD *)a1;
    }
LABEL_20:
    if ( v7 < *(_DWORD *)(v17 + v16 + 32) )
      break;
    ++v15;
  }
LABEL_25:
  v20 = v24;
  CBsString::_Release((CBsString *)&String2);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v24);
  return v20;
}

```

## disassembly

```asm
0x18000c258  push    rbp
0x18000c25a  push    rbx
0x18000c25b  push    rsi
0x18000c25c  push    rdi
0x18000c25d  push    r12
0x18000c25f  push    r13
0x18000c261  push    r14
0x18000c263  push    r15
0x18000c265  mov     rbp, rsp
0x18000c268  sub     rsp, 78h
0x18000c26c  mov     r12, r8
0x18000c26f  mov     r13, rdx
0x18000c272  mov     rbx, rcx
0x18000c275  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c27c  lea     rax, WPP_GLOBAL_Control
0x18000c283  cmp     rcx, rax
0x18000c286  jz      short loc_18000C2A6
0x18000c288  test    dword ptr [rcx+1Ch], 20000000h
0x18000c28f  jz      short loc_18000C2A6
0x18000c291  mov     rcx, [rcx+10h]
0x18000c295  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000c29c  mov     edx, 24h ; '$'
0x18000c2a1  call    WPP_SF_
0x18000c2a6  mov     r8d, 35Ch; unsigned __int16
0x18000c2ac  lea     rdx, aCsrdrvwuhelper_1; "CSrDrvWuHelper::_GetBootVolumeProp"
0x18000c2b3  lea     rcx, [rbp+var_48]; this
0x18000c2b7  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000c2bc  lea     rax, qword_18001A620
0x18000c2c3  xor     r14d, r14d
0x18000c2c6  mov     [rbp+String2], rax
0x18000c2ca  mov     eax, 360h
0x18000c2cf  mov     [rbp+var_50], r14
0x18000c2d3  test    rbx, rbx
0x18000c2d6  jz      loc_18000C42F
0x18000c2dc  mov     [rbp+var_44], ax
0x18000c2e0  mov     eax, 361h
0x18000c2e5  test    r13, r13
0x18000c2e8  jz      loc_18000C42F
0x18000c2ee  mov     [rbp+var_44], ax
0x18000c2f2  mov     eax, 362h
0x18000c2f7  test    r12, r12
0x18000c2fa  jz      loc_18000C42F
0x18000c300  mov     [rbp+var_44], ax
0x18000c304  lea     ecx, [r14+50h]
0x18000c308  mov     rax, r13
0x18000c30b  mov     [rbp+var_48], r14d
0x18000c30f  mov     [rax], r14b
0x18000c312  inc     rax
0x18000c315  sub     rcx, 1
0x18000c319  jnz     short loc_18000C30F
0x18000c31b  mov     rdx, [rbx+38h]; unsigned __int16 *
0x18000c31f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c323  mov     [r12], r14d
0x18000c327  inc     rax
0x18000c32a  cmp     [rdx+rax*2], r14w
0x18000c32f  jnz     short loc_18000C327
0x18000c331  cmp     rax, 3
0x18000c335  mov     eax, 367h
0x18000c33a  jb      loc_18000C42F
0x18000c340  mov     [rbp+var_48], r14d
0x18000c344  mov     [rbp+var_44], ax
0x18000c348  lea     rcx, [rbp+String2]; this
0x18000c34c  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000c351  mov     [rbp+var_48], eax
0x18000c354  test    eax, eax
0x18000c356  mov     eax, 369h
0x18000c35b  js      loc_18000C436
0x18000c361  cmp     dword ptr [rbp+var_50+4], 3
0x18000c365  mov     [rbp+var_44], ax
0x18000c369  mov     eax, 36Ah
0x18000c36e  jb      loc_18000C42F
0x18000c374  mov     rdx, [rbp+String2]; String2
0x18000c378  mov     dword ptr [rbp+var_50], 3
0x18000c37f  mov     [rdx+6], r14w
0x18000c384  mov     r15d, r14d
0x18000c387  mov     [rbp+var_48], r14d
0x18000c38b  mov     [rbp+var_44], ax
0x18000c38f  cmp     [rbx+50h], r14d
0x18000c393  jbe     loc_18000C43A
0x18000c399  mov     rsi, [rbx+58h]
0x18000c39d  mov     eax, r15d
0x18000c3a0  imul    rdi, rax, 38h ; '8'
0x18000c3a4  cmp     dword ptr [rdi+rsi+20h], 0
0x18000c3a9  jbe     short loc_18000C413
0x18000c3ab  mov     rcx, [rdi+rsi+28h]
0x18000c3b0  mov     eax, r14d
0x18000c3b3  mov     rcx, [rcx+rax*8]; String1
0x18000c3b7  call    cs:__imp__wcsicmp
0x18000c3bd  mov     rdx, [rbp+String2]
0x18000c3c1  test    eax, eax
0x18000c3c3  jz      short loc_18000C3D1
0x18000c3c5  inc     r14d
0x18000c3c8  cmp     r14d, [rdi+rsi+20h]
0x18000c3cd  jb      short loc_18000C3AB
0x18000c3cf  jmp     short loc_18000C413
0x18000c3d1  movups  xmm0, xmmword ptr [rdi+rsi]
0x18000c3d5  mov     dword ptr [r12], 1
0x18000c3dd  movups  xmmword ptr [r13+18h], xmm0
0x18000c3e2  movups  xmm1, xmmword ptr [rdi+rsi+10h]
0x18000c3e7  movups  xmmword ptr [r13+28h], xmm1
0x18000c3ec  movups  xmm0, xmmword ptr [rdi+rsi+20h]
0x18000c3f1  movups  xmmword ptr [r13+38h], xmm0
0x18000c3f6  movsd   xmm1, qword ptr [rdi+rsi+30h]
0x18000c3fc  movsd   qword ptr [r13+48h], xmm1
0x18000c402  mov     rax, [rbx+38h]
0x18000c406  mov     [r13+10h], rax
0x18000c40a  movups  xmm0, xmmword ptr [rbx]
0x18000c40d  movdqu  xmmword ptr [r13+0], xmm0
0x18000c413  cmp     r14d, [rdi+rsi+20h]
0x18000c418  jb      short loc_18000C43A
0x18000c41a  inc     r15d
0x18000c41d  mov     r14d, 0
0x18000c423  cmp     r15d, [rbx+50h]
0x18000c427  jb      loc_18000C399
0x18000c42d  jmp     short loc_18000C43A
0x18000c42f  mov     [rbp+var_48], 80070057h
0x18000c436  mov     [rbp+var_42], ax
0x18000c43a  mov     ebx, [rbp+var_48]
0x18000c43d  lea     rcx, [rbp+String2]; this
0x18000c441  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000c446  lea     rcx, [rbp+var_48]; this
0x18000c44a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000c44f  mov     eax, ebx
0x18000c451  add     rsp, 78h
0x18000c455  pop     r15
0x18000c457  pop     r14
0x18000c459  pop     r13
0x18000c45b  pop     r12
0x18000c45d  pop     rdi
0x18000c45e  pop     rsi
0x18000c45f  pop     rbx
0x18000c460  pop     rbp
0x18000c461  retn
```
