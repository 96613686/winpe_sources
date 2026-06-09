# NameTbl::GetDispID(ushort *,ulong,long *)

- ea: `0x1800362c0`
- end: `0x1800363ef`
- name: `?GetDispID@NameTbl@@UEAAJPEAGKPEAJ@Z`
- size: `303`
- prototype: `__int64 __fastcall(NameTbl *__hidden this, unsigned __int16 *, unsigned int, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800362c0`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800362df`
- `KERNEL32!GetCurrentThreadId` at `0x1800362df`

## pseudocode

```c
__int64 __fastcall NameTbl::GetDispID(NameTbl *this, unsigned __int16 *a2, char a3, int *a4)
{
  int v4; // ebx
  int v9; // r8d
  int v10; // ecx
  unsigned __int16 v11; // dx
  __int64 (__fastcall *v12)(NameTbl *, const wchar_t **, __int64 *, int *); // rax
  int v13; // eax
  int v14; // ecx
  const wchar_t *v16; // [rsp+30h] [rbp-28h] BYREF
  __int64 v17; // [rsp+38h] [rbp-20h]
  char v18; // [rsp+40h] [rbp-18h]
  bool v19; // [rsp+41h] [rbp-17h]
  int v20; // [rsp+42h] [rbp-16h]
  __int16 v21; // [rsp+46h] [rbp-12h]
  __int64 v22; // [rsp+90h] [rbp+38h] BYREF

  v4 = *((_DWORD *)this + 8);
  if ( GetCurrentThreadId() == v4 )
  {
    v22 = 0;
    v20 = 0;
    v21 = 0;
    if ( a2 )
    {
      v9 = 0;
      v10 = *((_DWORD *)a2 - 1) >> 1;
      LODWORD(v17) = v10;
      v16 = a2;
      if ( v10 )
      {
        do
        {
          v11 = *a2;
          --v10;
          ++a2;
          if ( (unsigned __int16)(v11 - 65) <= 0x19u )
            v11 += 32;
          v9 = v11 + 17 * v9;
        }
        while ( v10 > 0 );
      }
      HIDWORD(v17) = v9;
      v18 = 1;
    }
    else
    {
      v17 = 0;
      v16 = &String;
      v18 = 0;
    }
    v12 = *(__int64 (__fastcall **)(NameTbl *, const wchar_t **, __int64 *, int *))(*(_QWORD *)this + 240LL);
    v19 = (a3 & 1) != 0;
    v13 = v12(this, &v16, &v22, a4);
    v14 = v13;
    if ( v13 > 0 )
    {
      if ( (a3 & 2) != 0 )
        v14 = (*(__int64 (__fastcall **)(NameTbl *, const wchar_t **, _QWORD, _QWORD, int *))(*(_QWORD *)this + 120LL))(
                this,
                &v16,
                0,
                0,
                a4);
      else
        v14 = -2147352570;
    }
    else if ( !v13 )
    {
      if ( (*(_BYTE *)(v22 + 24) & 4) != 0 )
      {
        v14 = -2147352570;
LABEL_15:
        *a4 = -1;
      }
      return (unsigned int)v14;
    }
    if ( v14 < 0 )
      goto LABEL_15;
    return (unsigned int)v14;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800362c0  push    rbp
0x1800362c2  push    rbx
0x1800362c3  push    rsi
0x1800362c4  push    rdi
0x1800362c5  push    r14
0x1800362c7  push    r15
0x1800362c9  mov     rbp, rsp
0x1800362cc  sub     rsp, 58h
0x1800362d0  mov     ebx, [rcx+20h]
0x1800362d3  mov     r14, r9
0x1800362d6  mov     r15d, r8d
0x1800362d9  mov     rdi, rdx
0x1800362dc  mov     rsi, rcx
0x1800362df  call    cs:__imp_GetCurrentThreadId
0x1800362e5  cmp     eax, ebx
0x1800362e7  jnz     loc_1800363AF
0x1800362ed  xor     ebx, ebx
0x1800362ef  mov     [rbp+arg_0], rbx
0x1800362f3  mov     [rbp+var_16], ebx
0x1800362f6  mov     [rbp+var_12], bx
0x1800362fa  lea     r9d, [rbx+1]
0x1800362fe  test    rdi, rdi
0x180036301  jz      loc_1800363B6
0x180036307  mov     ecx, [rdi-4]
0x18003630a  mov     r8d, ebx
0x18003630d  shr     ecx, 1
0x18003630f  mov     dword ptr [rbp+var_20], ecx
0x180036312  mov     [rbp+var_28], rdi
0x180036316  jz      short loc_180036339
0x180036318  movzx   edx, word ptr [rdi]
0x18003631b  sub     ecx, r9d
0x18003631e  lea     rdi, [rdi+2]
0x180036322  lea     eax, [rdx-41h]
0x180036325  cmp     ax, 19h
0x180036329  jbe     short loc_180036384
0x18003632b  imul    r8d, 11h
0x18003632f  movzx   eax, dx
0x180036332  add     r8d, eax
0x180036335  test    ecx, ecx
0x180036337  jg      short loc_180036318
0x180036339  mov     dword ptr [rbp+var_20+4], r8d
0x18003633d  mov     [rbp+var_18], r9b
0x180036341  mov     rax, [rsi]
0x180036344  lea     r8, [rbp+arg_0]
0x180036348  test    r9b, r15b
0x18003634b  movzx   ecx, bl
0x18003634e  lea     rdx, [rbp+var_28]
0x180036352  cmovnz  ecx, r9d
0x180036356  mov     r9, r14
0x180036359  mov     rax, [rax+0F0h]
0x180036360  mov     [rbp+var_17], cl
0x180036363  mov     rcx, rsi
0x180036366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003636b  mov     ecx, eax
0x18003636d  test    eax, eax
0x18003636f  jg      short loc_18003638A
0x180036371  jnz     short loc_180036395
0x180036373  mov     rax, [rbp+arg_0]
0x180036377  test    byte ptr [rax+18h], 4
0x18003637b  jz      short loc_1800363A0
0x18003637d  mov     ecx, 80020006h
0x180036382  jmp     short loc_180036399
0x180036384  add     dx, 20h ; ' '
0x180036388  jmp     short loc_18003632B
0x18003638a  test    r15b, 2
0x18003638e  jnz     short loc_1800363CD
0x180036390  mov     ecx, 80020006h
0x180036395  test    ecx, ecx
0x180036397  jns     short loc_1800363A0
0x180036399  mov     dword ptr [r14], 0FFFFFFFFh
0x1800363a0  mov     eax, ecx
0x1800363a2  add     rsp, 58h
0x1800363a6  pop     r15
0x1800363a8  pop     r14
0x1800363aa  pop     rdi
0x1800363ab  pop     rsi
0x1800363ac  pop     rbx
0x1800363ad  pop     rbp
0x1800363ae  retn
0x1800363af  mov     eax, 8000FFFFh
0x1800363b4  jmp     short loc_1800363A2
0x1800363b6  lea     rax, String
0x1800363bd  mov     [rbp+var_20], rbx
0x1800363c1  mov     [rbp+var_28], rax
0x1800363c5  mov     [rbp+var_18], bl
0x1800363c8  jmp     loc_180036341
0x1800363cd  mov     rax, [rsi]
0x1800363d0  lea     rdx, [rbp+var_28]
0x1800363d4  xor     r9d, r9d
0x1800363d7  mov     [rsp+58h+var_38], r14
0x1800363dc  xor     r8d, r8d
0x1800363df  mov     rcx, rsi
0x1800363e2  mov     rax, [rax+78h]
0x1800363e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363eb  mov     ecx, eax
0x1800363ed  jmp     short loc_180036395
```
