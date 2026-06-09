# WinStationEnumerateExW

- ea: `0x180011cb0`
- end: `0x180011f9a`
- name: `WinStationEnumerateExW`
- size: `746`
- prototype: `char __fastcall(void *, _QWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180009ba4`
- `0x180009c10`
- `0x180011cb0`
- `0x180011fa0`
- `0x180013ee0`
- `0x18002fe06`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011d55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011d55`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011d99`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011d99`

## string_xrefs

- `0x180011d02`: `Failed to open binding`
- `0x180011d31`: `Enum->Open failed: 0x%x in %s`

## pseudocode

```c
char __fastcall WinStationEnumerateExW(void *a1, _QWORD *a2, _DWORD *a3)
{
  char v5; // bl
  void *v6; // rax
  __int64 v7; // rdx
  int EnumResult; // edi
  DWORD v9; // ecx
  unsigned int v10; // eax
  size_t v11; // rsi
  _BYTE *v12; // rax
  _BYTE *v13; // rdi
  unsigned int v14; // r8d
  unsigned __int64 i; // r9
  __int64 v16; // r11
  __int64 v17; // rdx
  __int64 v18; // r10
  __int64 v19; // rcx
  _WORD *v20; // rsi
  _WORD *v21; // rax
  _WORD *v22; // rcx
  _OWORD *v23; // rax
  __int64 v24; // rdx
  _OWORD *v25; // rcx
  __int128 v26; // xmm1
  unsigned __int16 v28[8]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v29; // [rsp+78h] [rbp+48h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+50h] BYREF
  __int64 v31; // [rsp+88h] [rbp+58h] BYREF

  *a2 = 0;
  *a3 = 0;
  hMem = 0;
  v29 = 0;
  v5 = 0;
  v31 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v28, a1, 0);
  if ( !CSmartPublicBinding::operator void *(v28) )
  {
    _DbgPrintMessage(8, "Failed to open binding");
    goto LABEL_31;
  }
  v6 = (void *)CSmartPublicBinding::operator void *(v28);
  EnumResult = CEnum::Open((CEnum *)&v31, v6);
  if ( EnumResult < 0 )
  {
    _DbgPrintMessage(8, "Enum->Open failed: 0x%x in %s", (unsigned int)EnumResult, "WinStationEnumerateExW");
LABEL_5:
    v9 = ConvertHRESULT2WIN32(EnumResult);
LABEL_6:
    SetLastError(v9);
    goto LABEL_31;
  }
  EnumResult = CEnum::GetEnumResultEx((CEnum *)&v31, v7, (struct _SESSIONENUM_EX **)&hMem, &v29);
  if ( EnumResult < 0 )
  {
    _DbgPrintMessage(8, "GetEnumResultEx failed: 0x%x in %s", (unsigned int)EnumResult, "WinStationEnumerateExW");
    goto LABEL_5;
  }
  v10 = 1112 * v29;
  if ( 1112 * v29 )
  {
    v11 = v10;
    v12 = LocalAlloc(0, v10);
    v13 = v12;
    if ( !v12 )
    {
      v9 = 8;
      goto LABEL_6;
    }
    memset_0(v12, 0, v11);
    v14 = 0;
    v5 = 1;
    for ( i = v11 / 0x458; v14 < (unsigned int)i; ++v14 )
    {
      if ( v14 >= v29 )
        break;
      v16 = 33;
      v17 = 120LL * v14;
      v18 = 1112LL * v14;
      *(_DWORD *)&v13[v18] = *(_DWORD *)((char *)hMem + v17 + 8);
      *(_DWORD *)&v13[v18 + 4] = *(_DWORD *)((char *)hMem + v17 + 12);
      v19 = 2147483646;
      v20 = (char *)hMem + v17 + 16;
      v21 = &v13[v18 + 32];
      do
      {
        if ( !v19 )
          break;
        if ( !*v20 )
          break;
        *v21++ = *v20++;
        --v19;
        --v16;
      }
      while ( v16 );
      v22 = v21 - 1;
      if ( v16 )
        v22 = v21;
      *v22 = 0;
      if ( *(_DWORD *)((char *)hMem + v17) >= 2u )
      {
        *(_DWORD *)&v13[v18 + 8] = *(_DWORD *)((char *)hMem + v17 + 84);
        *(_OWORD *)&v13[v18 + 16] = *(_OWORD *)((char *)hMem + v17 + 92);
        v13[v18 + 12] = *((_BYTE *)hMem + v17 + 88);
      }
      if ( *(_DWORD *)((char *)hMem + v17) == 3 )
      {
        v23 = *(_OWORD **)((char *)hMem + v17 + 112);
        if ( v23 )
        {
          if ( *(_DWORD *)((char *)hMem + v17 + 108) >= 0x3F4u )
          {
            v24 = 7;
            v25 = &v13[v18 + 100];
            do
            {
              *v25 = *v23;
              v25[1] = v23[1];
              v25[2] = v23[2];
              v25[3] = v23[3];
              v25[4] = v23[4];
              v25[5] = v23[5];
              v25[6] = v23[6];
              v26 = v23[7];
              v23 += 8;
              v25[7] = v26;
              v25 += 8;
              --v24;
            }
            while ( v24 );
            *v25 = *v23;
            v25[1] = v23[1];
            v25[2] = v23[2];
            v25[3] = v23[3];
            v25[4] = v23[4];
            v25[5] = v23[5];
            v25[6] = v23[6];
            *((_DWORD *)v25 + 28) = *((_DWORD *)v23 + 28);
          }
        }
      }
    }
    *a2 = v13;
    *a3 = i;
  }
  else
  {
    v5 = 1;
  }
LABEL_31:
  if ( hMem )
    CEnum::FreeEnumResultEx(hMem, v29);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v28);
  CEnum::~CEnum((CEnum *)&v31);
  return v5;
}

```

## disassembly

```asm
0x180011cb0  mov     [rsp-38h+arg_0], rbx
0x180011cb5  push    rbp
0x180011cb6  push    rsi
0x180011cb7  push    rdi
0x180011cb8  push    r12
0x180011cba  push    r13
0x180011cbc  push    r14
0x180011cbe  push    r15
0x180011cc0  mov     rbp, rsp
0x180011cc3  sub     rsp, 30h
0x180011cc7  xor     r13d, r13d
0x180011cca  mov     r12, rdx
0x180011ccd  mov     [rdx], r13
0x180011cd0  mov     r15, r8
0x180011cd3  mov     [r8], r13d
0x180011cd6  mov     rdx, rcx; void *
0x180011cd9  xor     r8d, r8d; int
0x180011cdc  mov     [rbp+hMem], r13
0x180011ce0  lea     rcx, [rbp+var_10]; this
0x180011ce4  mov     [rbp+arg_8], r13d
0x180011ce8  mov     bl, r13b
0x180011ceb  mov     [rbp+arg_18], r13
0x180011cef  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180011cf4  lea     rcx, [rbp+var_10]; unsigned __int16 *
0x180011cf8  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180011cfd  test    rax, rax
0x180011d00  jnz     short loc_180011D16
0x180011d02  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180011d09  lea     ecx, [rax+8]; int
0x180011d0c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011d11  jmp     loc_180011F60
0x180011d16  lea     rcx, [rbp+var_10]; unsigned __int16 *
0x180011d1a  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180011d1f  mov     rdx, rax; void *
0x180011d22  lea     rcx, [rbp+arg_18]; this
0x180011d26  call    ?Open@CEnum@@QEAAJPEAX@Z; CEnum::Open(void *)
0x180011d2b  mov     edi, eax
0x180011d2d  test    eax, eax
0x180011d2f  jns     short loc_180011D60
0x180011d31  lea     rdx, aEnumOpenFailed; "Enum->Open failed: 0x%x in %s"
0x180011d38  mov     r8d, edi
0x180011d3b  lea     r9, aWinstationenum_9; "WinStationEnumerateExW"
0x180011d42  mov     ecx, 8; int
0x180011d47  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011d4c  mov     ecx, edi; int
0x180011d4e  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180011d53  mov     ecx, eax; dwErrCode
0x180011d55  call    cs:__imp_SetLastError
0x180011d5b  jmp     loc_180011F60
0x180011d60  lea     r9, [rbp+arg_8]; unsigned int *
0x180011d64  lea     r8, [rbp+hMem]; struct _SESSIONENUM_EX **
0x180011d68  lea     rcx, [rbp+arg_18]; this
0x180011d6c  call    ?GetEnumResultEx@CEnum@@QEAAJKPEAPEAU_SESSIONENUM_EX@@PEAK@Z; CEnum::GetEnumResultEx(ulong,_SESSIONENUM_EX * *,ulong *)
0x180011d71  mov     edi, eax
0x180011d73  test    eax, eax
0x180011d75  jns     short loc_180011D80
0x180011d77  lea     rdx, aGetenumresulte; "GetEnumResultEx failed: 0x%x in %s"
0x180011d7e  jmp     short loc_180011D38
0x180011d80  imul    eax, [rbp+arg_8], 458h
0x180011d87  test    eax, eax
0x180011d89  jnz     short loc_180011D93
0x180011d8b  lea     ebx, [rax+1]
0x180011d8e  jmp     loc_180011F60
0x180011d93  mov     edx, eax; uBytes
0x180011d95  xor     ecx, ecx; uFlags
0x180011d97  mov     esi, eax
0x180011d99  call    cs:__imp_LocalAlloc
0x180011d9f  mov     rdi, rax
0x180011da2  test    rax, rax
0x180011da5  jnz     short loc_180011DAC
0x180011da7  lea     ecx, [rax+8]
0x180011daa  jmp     short loc_180011D55
0x180011dac  mov     r8, rsi; Size
0x180011daf  xor     edx, edx; Val
0x180011db1  mov     rcx, rdi; void *
0x180011db4  call    memset_0
0x180011db9  mov     rax, 3AEF6CA970586723h
0x180011dc3  mov     r8d, r13d
0x180011dc6  mul     rsi
0x180011dc9  mov     ebx, 1
0x180011dce  mov     r9, rdx
0x180011dd1  shr     r9, 8
0x180011dd5  test    r9d, r9d
0x180011dd8  jz      loc_180011F59
0x180011dde  cmp     r8d, [rbp+arg_8]
0x180011de2  jnb     loc_180011F59
0x180011de8  mov     eax, r8d
0x180011deb  mov     r11d, 21h ; '!'
0x180011df1  imul    rdx, rax, 78h ; 'x'
0x180011df5  imul    r10, rax, 458h
0x180011dfc  mov     rax, [rbp+hMem]
0x180011e00  mov     ecx, [rdx+rax+8]
0x180011e04  mov     [r10+rdi], ecx
0x180011e08  mov     rax, [rbp+hMem]
0x180011e0c  mov     ecx, [rdx+rax+0Ch]
0x180011e10  lea     rax, [rdi+20h]
0x180011e14  mov     [r10+rdi+4], ecx
0x180011e19  mov     ecx, 7FFFFFFEh
0x180011e1e  mov     rsi, [rbp+hMem]
0x180011e22  add     rsi, 10h
0x180011e26  add     rsi, rdx
0x180011e29  add     rax, r10
0x180011e2c  test    rcx, rcx
0x180011e2f  jz      short loc_180011E4F
0x180011e31  movzx   r14d, word ptr [rsi]
0x180011e35  test    r14w, r14w
0x180011e39  jz      short loc_180011E4F
0x180011e3b  mov     [rax], r14w
0x180011e3f  add     rsi, 2
0x180011e43  add     rax, 2
0x180011e47  sub     rcx, rbx
0x180011e4a  sub     r11, rbx
0x180011e4d  jnz     short loc_180011E2C
0x180011e4f  test    r11, r11
0x180011e52  lea     rcx, [rax-2]
0x180011e56  cmovnz  rcx, rax
0x180011e5a  mov     [rcx], r13w
0x180011e5e  mov     rax, [rbp+hMem]
0x180011e62  cmp     dword ptr [rdx+rax], 2
0x180011e66  jb      short loc_180011E8E
0x180011e68  mov     eax, [rdx+rax+54h]
0x180011e6c  mov     [r10+rdi+8], eax
0x180011e71  mov     rax, [rbp+hMem]
0x180011e75  movups  xmm0, xmmword ptr [rdx+rax+5Ch]
0x180011e7a  movdqu  xmmword ptr [r10+rdi+10h], xmm0
0x180011e81  mov     rax, [rbp+hMem]
0x180011e85  mov     cl, [rdx+rax+58h]
0x180011e89  mov     [r10+rdi+0Ch], cl
0x180011e8e  mov     rcx, [rbp+hMem]
0x180011e92  cmp     dword ptr [rdx+rcx], 3
0x180011e96  jnz     loc_180011F4D
0x180011e9c  mov     rax, [rdx+rcx+70h]
0x180011ea1  test    rax, rax
0x180011ea4  jz      loc_180011F4D
0x180011eaa  cmp     dword ptr [rdx+rcx+6Ch], 3F4h
0x180011eb2  jb      loc_180011F4D
0x180011eb8  mov     edx, 7
0x180011ebd  lea     rcx, [rdi+64h]
0x180011ec1  add     rcx, r10
0x180011ec4  lea     r14d, [rdx+79h]
0x180011ec8  movups  xmm0, xmmword ptr [rax]
0x180011ecb  movups  xmmword ptr [rcx], xmm0
0x180011ece  movups  xmm1, xmmword ptr [rax+10h]
0x180011ed2  movups  xmmword ptr [rcx+10h], xmm1
0x180011ed6  movups  xmm0, xmmword ptr [rax+20h]
0x180011eda  movups  xmmword ptr [rcx+20h], xmm0
0x180011ede  movups  xmm1, xmmword ptr [rax+30h]
0x180011ee2  movups  xmmword ptr [rcx+30h], xmm1
0x180011ee6  movups  xmm0, xmmword ptr [rax+40h]
0x180011eea  movups  xmmword ptr [rcx+40h], xmm0
0x180011eee  movups  xmm1, xmmword ptr [rax+50h]
0x180011ef2  movups  xmmword ptr [rcx+50h], xmm1
0x180011ef6  movups  xmm0, xmmword ptr [rax+60h]
0x180011efa  movups  xmmword ptr [rcx+60h], xmm0
0x180011efe  movups  xmm1, xmmword ptr [rax+70h]
0x180011f02  add     rax, r14
0x180011f05  movups  xmmword ptr [rcx+70h], xmm1
0x180011f09  add     rcx, r14
0x180011f0c  sub     rdx, rbx
0x180011f0f  jnz     short loc_180011EC8
0x180011f11  movups  xmm0, xmmword ptr [rax]
0x180011f14  movups  xmmword ptr [rcx], xmm0
0x180011f17  movups  xmm1, xmmword ptr [rax+10h]
0x180011f1b  movups  xmmword ptr [rcx+10h], xmm1
0x180011f1f  movups  xmm0, xmmword ptr [rax+20h]
0x180011f23  movups  xmmword ptr [rcx+20h], xmm0
0x180011f27  movups  xmm1, xmmword ptr [rax+30h]
0x180011f2b  movups  xmmword ptr [rcx+30h], xmm1
0x180011f2f  movups  xmm0, xmmword ptr [rax+40h]
0x180011f33  movups  xmmword ptr [rcx+40h], xmm0
0x180011f37  movups  xmm1, xmmword ptr [rax+50h]
0x180011f3b  movups  xmmword ptr [rcx+50h], xmm1
0x180011f3f  movups  xmm0, xmmword ptr [rax+60h]
0x180011f43  movups  xmmword ptr [rcx+60h], xmm0
0x180011f47  mov     eax, [rax+70h]
0x180011f4a  mov     [rcx+70h], eax
0x180011f4d  add     r8d, ebx
0x180011f50  cmp     r8d, r9d
0x180011f53  jb      loc_180011DDE
0x180011f59  mov     [r12], rdi
0x180011f5d  mov     [r15], r9d
0x180011f60  mov     rcx, [rbp+hMem]; hMem
0x180011f64  test    rcx, rcx
0x180011f67  jz      short loc_180011F71
0x180011f69  mov     edx, [rbp+arg_8]; unsigned int
0x180011f6c  call    ?FreeEnumResultEx@CEnum@@SAJPEAU_SESSIONENUM_EX@@K@Z; CEnum::FreeEnumResultEx(_SESSIONENUM_EX *,ulong)
0x180011f71  lea     rcx, [rbp+var_10]; this
0x180011f75  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180011f7a  lea     rcx, [rbp+arg_18]; this
0x180011f7e  call    ??1CEnum@@QEAA@XZ; CEnum::~CEnum(void)
0x180011f83  mov     al, bl
0x180011f85  mov     rbx, [rsp+30h+arg_0]
0x180011f8a  add     rsp, 30h
0x180011f8e  pop     r15
0x180011f90  pop     r14
0x180011f92  pop     r13
0x180011f94  pop     r12
0x180011f96  pop     rdi
0x180011f97  pop     rsi
0x180011f98  pop     rbp
0x180011f99  retn
```
