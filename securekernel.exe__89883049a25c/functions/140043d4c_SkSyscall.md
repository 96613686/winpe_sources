# SkSyscall

- ea: `0x140043d4c`
- end: `0x1400440ad`
- name: `SkSyscall`
- size: `865`
- prototype: `__int64 __fastcall(unsigned int, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1400ef510`

## callees

- `0x14002ba08`
- `0x140040f54`
- `0x140043d4c`
- `0x1400b71b8`
- `0x1400b7674`
- `0x1400ee8b0`
- `0x1400f3620`
- `0x1400f9780`
- `0x1400f9a80`

## string_xrefs

- `0x140043dc2`: `ERROR :Invalid ServiceNumber 0x%x`

## pseudocode

```c
__int64 __fastcall SkSyscall(unsigned int a1, void *a2)
{
  _BYTE *StackBase; // rax
  __int64 v4; // rsi
  int v5; // ebx
  unsigned __int64 v7; // rdi
  __int64 v8; // rbx
  unsigned int v9; // r12d
  unsigned int v10; // r15d
  unsigned int v11; // r14d
  __int64 (__fastcall *v12)(unsigned int, __int64, __int64, __int64, unsigned __int8, __int64, _DWORD *, __int64); // rax
  unsigned __int8 v13; // r12
  char *v14; // r14
  __int64 SyscallBuffer; // rdi
  int v16; // eax
  char v17; // [rsp+48h] [rbp-B8h]
  char v18; // [rsp+60h] [rbp-A0h]
  unsigned int v19; // [rsp+64h] [rbp-9Ch] BYREF
  void *Src; // [rsp+68h] [rbp-98h]
  __int64 v21; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+78h] [rbp-88h]
  _BYTE v23[48]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v24[12]; // [rsp+110h] [rbp+10h] BYREF
  char v25[176]; // [rsp+170h] [rbp+70h] BYREF

  Src = a2;
  memset_0(v24, 0, sizeof(v24));
  memset_0(&v21, 0, 0x68u);
  StackBase = KeGetPcr()->NtTib.StackBase;
  v4 = a1;
  LODWORD(v4) = a1 & 0x7FFFFFFF;
  v19 = 0;
  if ( (a1 & 0x7FFFFFFF) >= IumSyscallDescriptorLimit )
  {
    DbgPrint("ERROR :Invalid ServiceNumber 0x%x", v4);
    return (unsigned int)-1073741796;
  }
  v7 = (unsigned int)IumSyscallDescriptor[v4];
  v8 = 0;
  v18 = StackBase[96];
  v9 = (unsigned int)IumSyscallDescriptor[v4] >> 12;
  v10 = (unsigned __int8)HIBYTE(LOWORD(IumSyscallDescriptor[v4])) >> 4;
  if ( (v9 & 0xF) == 0 )
    goto LABEL_9;
  memmove(v24, Src, 8LL * (v9 & 0xF));
  do
    v8 = (unsigned int)(v8 + 1);
  while ( (unsigned int)v8 < v10 );
  if ( (unsigned int)v8 < 0xC )
LABEL_9:
    memset_0(&v24[v8], 0, 8LL * (unsigned int)(12 - v8));
  if ( (v7 & 0x30000) == 0 )
    return (unsigned int)-1073741796;
  v11 = a1 >> 31;
  if ( (v7 & 0x30000) == 0x30000 && !(_BYTE)v11 )
    return (unsigned int)-1073741796;
  if ( v10 + (v7 & 0xFFF) >= 0x707 )
    return (unsigned int)-1073741796;
  LODWORD(Src) = v18 == 1;
  if ( (v7 & 0x7C0000) >= 0x80000 )
    return (unsigned int)-1073741796;
  v12 = (__int64 (__fastcall *)(unsigned int, __int64, __int64, __int64, unsigned __int8, __int64, _DWORD *, __int64))*(&IumSyscallCustomApiFcnTable + ((v7 >> 18) & 0x1F));
  if ( !v12 )
    return (unsigned int)-1073741796;
  v17 = (v7 & 0x800000) != 0 ? v11 : 0;
  v13 = v9 & 0xF;
  v14 = (char *)IumSyscallArgDescriptor + 4 * (v7 & 0xFFF);
  if ( v12 == IumApi_NtGENERIC )
  {
    v5 = IumApi_NtGENERIC(0, (__int64)v14, (__int64)v24, (__int64)&v21, v13, 0, &v19, (__int64)v23);
    if ( v5 >= 0 )
    {
      SyscallBuffer = 0;
      if ( !v19 || (SyscallBuffer = SkAllocateSyscallBuffer(v19, (unsigned int)Src)) != 0 )
      {
        v5 = IumApi_NtGENERIC(1u, (__int64)v14, (__int64)v24, (__int64)&v21, v13, SyscallBuffer, &v19, (__int64)v23);
        if ( v5 >= 0 )
        {
          v21 = 0;
          *(_DWORD *)((char *)&v21 + 1) = (unsigned __int8)((v18 != 1) + 2);
          WORD1(v21) = v4;
          SkCallNormalMode(&v21);
          v5 = v22;
          if ( v22 >= 0 || v22 == -1073741820 || v22 == -2147483643 || v22 == -1073741789 )
          {
            v16 = IumApi_NtGENERIC(
                    2u,
                    (__int64)v14,
                    (__int64)v24,
                    (__int64)&v21,
                    v13,
                    SyscallBuffer,
                    &v19,
                    (__int64)v23);
            if ( v16 < 0 )
              v5 = v16;
          }
        }
        if ( v19 )
          SkFreeSyscallBuffer(SyscallBuffer);
      }
      else
      {
        return (unsigned int)-1073741801;
      }
    }
  }
  else
  {
    return ((unsigned int (__fastcall *)(__int64, char *, _QWORD *, __int64 *, unsigned __int8, _QWORD, _QWORD, _BYTE *, char *, char, _BYTE))v12)(
             3,
             v14,
             v24,
             &v21,
             v13,
             0,
             0,
             v23,
             v25,
             v17,
             0);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140043d4c  push    rbp
0x140043d4e  push    rbx
0x140043d4f  push    rsi
0x140043d50  push    rdi
0x140043d51  push    r12
0x140043d53  push    r13
0x140043d55  push    r14
0x140043d57  push    r15
0x140043d59  lea     rbp, [rsp-138h]
0x140043d61  sub     rsp, 238h
0x140043d68  mov     rax, cs:__security_cookie
0x140043d6f  xor     rax, rsp
0x140043d72  mov     [rbp+170h+var_50], rax
0x140043d79  mov     [rsp+270h+Src], rdx
0x140043d7e  mov     r14d, ecx
0x140043d81  xor     edx, edx; Val
0x140043d83  lea     rcx, [rbp+170h+var_160]; void *
0x140043d87  lea     r8d, [rdx+60h]; Size
0x140043d8b  call    memset_0
0x140043d90  xor     edx, edx; Val
0x140043d92  lea     rcx, [rsp+270h+var_200]; void *
0x140043d97  lea     r8d, [rdx+68h]; Size
0x140043d9b  call    memset_0
0x140043da0  mov     rax, gs:8
0x140043da9  mov     esi, r14d
0x140043dac  btr     esi, 1Fh
0x140043db0  mov     [rsp+270h+var_20C], 0
0x140043db8  cmp     esi, cs:IumSyscallDescriptorLimit
0x140043dbe  jb      short loc_140043DF9
0x140043dc0  mov     edx, esi
0x140043dc2  lea     rcx, aErrorInvalidSe; "ERROR :Invalid ServiceNumber 0x%x"
0x140043dc9  call    DbgPrint
0x140043dce  mov     ebx, 0C000001Ch
0x140043dd3  mov     eax, ebx
0x140043dd5  mov     rcx, [rbp+170h+var_50]
0x140043ddc  xor     rcx, rsp; StackCookie
0x140043ddf  call    __security_check_cookie
0x140043de4  add     rsp, 238h
0x140043deb  pop     r15
0x140043ded  pop     r14
0x140043def  pop     r13
0x140043df1  pop     r12
0x140043df3  pop     rdi
0x140043df4  pop     rsi
0x140043df5  pop     rbx
0x140043df6  pop     rbp
0x140043df7  retn
0x140043df9  mov     al, [rax+60h]
0x140043dfc  lea     rcx, cs:140000000h
0x140043e03  mov     edi, rva IumSyscallDescriptor[rcx+rsi*4]
0x140043e0a  xor     ebx, ebx
0x140043e0c  mov     r12d, edi
0x140043e0f  mov     [rsp+270h+var_210], al
0x140043e13  shr     r12d, 0Ch
0x140043e17  mov     r15d, r12d
0x140043e1a  lea     r13d, [rbx+0Ch]
0x140043e1e  and     r15d, 0Fh
0x140043e22  jz      short loc_140043E45
0x140043e24  mov     rdx, [rsp+270h+Src]; Src
0x140043e29  lea     rcx, [rbp+170h+var_160]; void *
0x140043e2d  mov     r8d, r15d
0x140043e30  shl     r8, 3; Size
0x140043e34  call    memmove
0x140043e39  inc     ebx
0x140043e3b  cmp     ebx, r15d
0x140043e3e  jb      short loc_140043E39
0x140043e40  cmp     ebx, r13d
0x140043e43  jnb     short loc_140043E5E
0x140043e45  sub     r13d, ebx
0x140043e48  lea     rcx, [rbp+170h+var_160]
0x140043e4c  mov     r8d, r13d
0x140043e4f  lea     rcx, [rcx+rbx*8]; void *
0x140043e53  shl     r8, 3; Size
0x140043e57  xor     edx, edx; Val
0x140043e59  call    memset_0
0x140043e5e  mov     eax, edi
0x140043e60  mov     ecx, 30000h
0x140043e65  and     eax, ecx
0x140043e67  jz      loc_140043DCE
0x140043e6d  shr     r14d, 1Fh
0x140043e71  xor     edx, edx
0x140043e73  cmp     eax, ecx
0x140043e75  jnz     short loc_140043E80
0x140043e77  test    r14b, r14b
0x140043e7a  jz      loc_140043DCE
0x140043e80  mov     eax, edi
0x140043e82  mov     r8d, 0FFFh
0x140043e88  and     eax, r8d
0x140043e8b  add     eax, r15d
0x140043e8e  cmp     eax, 707h
0x140043e93  jnb     loc_140043DCE
0x140043e99  cmp     [rsp+270h+var_210], 1
0x140043e9e  mov     eax, edx
0x140043ea0  setz    al
0x140043ea3  setnz   r13b
0x140043ea7  mov     dword ptr [rsp+270h+Src], eax
0x140043eab  add     r13b, 2
0x140043eaf  mov     eax, edi
0x140043eb1  and     eax, 7C0000h
0x140043eb6  cmp     eax, 80000h
0x140043ebb  jnb     loc_140043DCE
0x140043ec1  mov     rcx, rdi
0x140043ec4  lea     r9, cs:140000000h
0x140043ecb  and     edi, 800000h
0x140043ed1  mov     rax, rcx
0x140043ed4  neg     edi
0x140043ed6  sbb     r15b, r15b
0x140043ed9  shr     rax, 12h
0x140043edd  and     eax, 1Fh
0x140043ee0  and     r15b, r14b
0x140043ee3  mov     rax, ds:rva IumSyscallCustomApiFcnTable[r9+rax*8]
0x140043eeb  test    rax, rax
0x140043eee  jz      loc_140043DCE
0x140043ef4  and     rcx, r8
0x140043ef7  mov     [rsp+270h+var_220], dl
0x140043efb  lea     r14, rva IumSyscallArgDescriptor[r9]
0x140043f02  mov     [rsp+270h+var_228], r15b
0x140043f07  and     r12b, 0Fh
0x140043f0b  lea     r9, [rsp+270h+var_200]
0x140043f10  lea     r8, [rbp+170h+var_160]
0x140043f14  lea     r14, [r14+rcx*4]
0x140043f18  lea     rcx, IumApi_NtGENERIC
0x140043f1f  cmp     rax, rcx
0x140043f22  jz      short loc_140043F59
0x140043f24  lea     rcx, [rbp+170h+var_100]
0x140043f28  mov     [rsp+270h+var_230], rcx
0x140043f2d  lea     rcx, [rbp+170h+var_190]
0x140043f31  mov     [rsp+270h+var_238], rcx
0x140043f36  mov     ecx, 3
0x140043f3b  mov     [rsp+270h+var_240], rdx
0x140043f40  mov     [rsp+270h+var_248], rdx
0x140043f45  mov     rdx, r14
0x140043f48  mov     [rsp+270h+var_250], r12b
0x140043f4d  call    rax
0x140043f4f  nop     dword ptr [rax]
0x140043f52  mov     ebx, eax
0x140043f54  jmp     loc_140043DD3
0x140043f59  lea     rax, [rbp+170h+var_100]
0x140043f5d  xor     ecx, ecx
0x140043f5f  mov     [rsp+270h+var_230], rax
0x140043f64  lea     rax, [rbp+170h+var_190]
0x140043f68  mov     [rsp+270h+var_238], rax
0x140043f6d  lea     rax, [rsp+270h+var_20C]
0x140043f72  mov     [rsp+270h+var_240], rax
0x140043f77  mov     [rsp+270h+var_248], rdx
0x140043f7c  mov     rdx, r14
0x140043f7f  mov     [rsp+270h+var_250], r12b
0x140043f84  call    IumApi_NtGENERIC
0x140043f89  mov     ebx, eax
0x140043f8b  test    eax, eax
0x140043f8d  js      loc_140043DD3
0x140043f93  mov     ecx, [rsp+270h+var_20C]
0x140043f97  xor     edi, edi
0x140043f99  test    ecx, ecx
0x140043f9b  jz      short loc_140043FB8
0x140043f9d  mov     edx, dword ptr [rsp+270h+Src]
0x140043fa1  call    SkAllocateSyscallBuffer
0x140043fa6  mov     rdi, rax
0x140043fa9  test    rax, rax
0x140043fac  jnz     short loc_140043FB8
0x140043fae  mov     ebx, 0C0000017h
0x140043fb3  jmp     loc_140043DD3
0x140043fb8  mov     [rsp+270h+var_220], 0
0x140043fbd  lea     rax, [rbp+170h+var_100]
0x140043fc1  mov     [rsp+270h+var_228], r15b
0x140043fc6  lea     r9, [rsp+270h+var_200]
0x140043fcb  mov     [rsp+270h+var_230], rax
0x140043fd0  lea     r8, [rbp+170h+var_160]
0x140043fd4  lea     rax, [rbp+170h+var_190]
0x140043fd8  mov     rdx, r14
0x140043fdb  mov     [rsp+270h+var_238], rax
0x140043fe0  mov     ecx, 1
0x140043fe5  lea     rax, [rsp+270h+var_20C]
0x140043fea  mov     [rsp+270h+var_240], rax
0x140043fef  mov     [rsp+270h+var_248], rdi
0x140043ff4  mov     [rsp+270h+var_250], r12b
0x140043ff9  call    IumApi_NtGENERIC
0x140043ffe  mov     ebx, eax
0x140044000  test    eax, eax
0x140044002  js      loc_140044094
0x140044008  mov     [rsp+270h+var_200], 0
0x140044011  lea     rcx, [rsp+270h+var_200]
0x140044016  mov     byte ptr [rsp+270h+var_200+1], r13b
0x14004401b  mov     word ptr [rsp+270h+var_200+2], si
0x140044020  call    SkCallNormalMode
0x140044025  mov     ebx, [rsp+270h+var_1F8]
0x140044029  test    ebx, ebx
0x14004402b  jns     short loc_140044047
0x14004402d  cmp     ebx, 0C0000004h
0x140044033  jz      short loc_140044045
0x140044035  cmp     ebx, 80000005h
0x14004403b  jz      short loc_140044045
0x14004403d  cmp     ebx, 0C0000023h
0x140044043  jnz     short loc_140044094
0x140044045  test    ebx, ebx
0x140044047  setnz   al
0x14004404a  lea     r9, [rsp+270h+var_200]
0x14004404f  mov     [rsp+270h+var_220], al
0x140044053  lea     r8, [rbp+170h+var_160]
0x140044057  mov     [rsp+270h+var_228], r15b
0x14004405c  lea     rax, [rbp+170h+var_100]
0x140044060  mov     [rsp+270h+var_230], rax
0x140044065  mov     rdx, r14
0x140044068  lea     rax, [rbp+170h+var_190]
0x14004406c  mov     ecx, 2
0x140044071  mov     [rsp+270h+var_238], rax
0x140044076  lea     rax, [rsp+270h+var_20C]
0x14004407b  mov     [rsp+270h+var_240], rax
0x140044080  mov     [rsp+270h+var_248], rdi
0x140044085  mov     [rsp+270h+var_250], r12b
0x14004408a  call    IumApi_NtGENERIC
0x14004408f  test    eax, eax
0x140044091  cmovs   ebx, eax
0x140044094  mov     edx, [rsp+270h+var_20C]
0x140044098  test    edx, edx
0x14004409a  jz      loc_140043DD3
0x1400440a0  mov     rcx, rdi
0x1400440a3  call    SkFreeSyscallBuffer
0x1400440a8  jmp     loc_140043DD3
```
