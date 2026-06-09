# LsapMarshallAuthData(_DLL_SECURITY_PACKAGE *,void *,void * *,ulong *)

- ea: `0x18000e8e4`
- end: `0x18000e9ad`
- name: `?LsapMarshallAuthData@@YAJPEAU_DLL_SECURITY_PACKAGE@@PEAXPEAPEAXPEAK@Z`
- size: `201`
- prototype: `SECURITY_STATUS __fastcall(struct _DLL_SECURITY_PACKAGE *, _DWORD *, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005190`
- `0x180010f00`

## callees

- `0x18000e8e4`
- `0x18000e9d0`
- `0x180018600`
- `0x180020540`
- `0x180023010`

## pseudocode

```c
SECURITY_STATUS __fastcall LsapMarshallAuthData(
        struct _DLL_SECURITY_PACKAGE *a1,
        _DWORD *a2,
        void **a3,
        unsigned int *a4)
{
  __int64 v6; // rax
  int v7; // ebx
  __int64 (__fastcall *v8)(_QWORD, _DWORD *, unsigned int *, void **); // rax
  SECURITY_STATUS result; // eax
  unsigned int *v10; // r9
  _BYTE *v11; // rdi
  int v12; // eax
  __int64 v13; // rdx
  _BYTE *v14; // rax
  PVOID DataBuffer; // [rsp+30h] [rbp-18h] BYREF
  unsigned int AuthIdentityLength; // [rsp+58h] [rbp+10h] BYREF

  if ( (unsigned int)(*a2 - 512) > 1 )
  {
    v6 = *((_QWORD *)a1 + 23);
    v7 = -1073741637;
    if ( v6 )
    {
      v8 = *(__int64 (__fastcall **)(_QWORD, _DWORD *, unsigned int *, void **))(v6 + 88);
      if ( v8 )
        return v8(0, a2, a4, a3);
    }
    return v7;
  }
  DataBuffer = 0;
  AuthIdentityLength = 0;
  result = SspiMarshalAuthIdentity(a2, &AuthIdentityLength, (char **)&DataBuffer);
  if ( result >= 0 )
  {
    v10 = a4;
    v11 = DataBuffer;
    v12 = SspiUnmarshalAuthIdentityInternal(AuthIdentityLength, (char *)DataBuffer, a3, v10);
    v13 = AuthIdentityLength;
    v7 = v12;
    v14 = v11;
    if ( AuthIdentityLength )
    {
      do
      {
        *v14++ = 0;
        --v13;
      }
      while ( v13 );
    }
    SspiLocalFree(v11);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18000e8e4  mov     [rsp+arg_0], rbx
0x18000e8e9  mov     [rsp+arg_10], rsi
0x18000e8ee  push    rdi
0x18000e8ef  sub     rsp, 40h
0x18000e8f3  mov     eax, [rdx]
0x18000e8f5  mov     rdi, r9
0x18000e8f8  sub     eax, 200h
0x18000e8fd  mov     rsi, r8
0x18000e900  mov     r10, rdx
0x18000e903  cmp     eax, 1
0x18000e906  jbe     short loc_18000E980
0x18000e908  mov     rax, [rcx+0B8h]
0x18000e90f  mov     ebx, 0C00000BBh
0x18000e914  test    rax, rax
0x18000e917  jz      short loc_18000E922
0x18000e919  mov     rax, [rax+58h]
0x18000e91d  test    rax, rax
0x18000e920  jnz     short loc_18000E934
0x18000e922  mov     eax, ebx
0x18000e924  mov     rbx, [rsp+48h+arg_0]
0x18000e929  mov     rsi, [rsp+48h+arg_10]
0x18000e92e  add     rsp, 40h
0x18000e932  pop     rdi
0x18000e933  retn
0x18000e934  mov     r9, rsi
0x18000e937  mov     r8, rdi
0x18000e93a  xor     ecx, ecx
0x18000e93c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e941  mov     ebx, eax
0x18000e943  jmp     short loc_18000E922
0x18000e945  mov     ecx, [rsp+48h+AuthIdentityLength]; Size
0x18000e949  mov     r9, rdi; unsigned int *
0x18000e94c  mov     rdi, [rsp+48h+DataBuffer]
0x18000e951  mov     r8, rsi; void **
0x18000e954  mov     rdx, rdi; Src
0x18000e957  call    ?SspiUnmarshalAuthIdentityInternal@@YAJKPEADPEAPEAXPEAK@Z; SspiUnmarshalAuthIdentityInternal(ulong,char *,void * *,ulong *)
0x18000e95c  mov     edx, [rsp+48h+AuthIdentityLength]
0x18000e960  mov     ebx, eax
0x18000e962  mov     rax, rdi
0x18000e965  test    rdx, rdx
0x18000e968  jz      short loc_18000E976
0x18000e96a  mov     byte ptr [rax], 0
0x18000e96d  inc     rax
0x18000e970  sub     rdx, 1
0x18000e974  jnz     short loc_18000E96A
0x18000e976  mov     rcx, rdi; DataBuffer
0x18000e979  call    SspiLocalFree
0x18000e97e  jmp     short loc_18000E922
0x18000e980  lea     r8, [rsp+48h+DataBuffer]; AuthIdentityByteArray
0x18000e985  mov     [rsp+48h+DataBuffer], 0
0x18000e98e  lea     rdx, [rsp+48h+AuthIdentityLength]; AuthIdentityLength
0x18000e993  mov     [rsp+48h+AuthIdentityLength], 0
0x18000e99b  mov     rcx, r10; AuthIdentity
0x18000e99e  call    SspiMarshalAuthIdentity
0x18000e9a3  test    eax, eax
0x18000e9a5  js      loc_18000E924
0x18000e9ab  jmp     short loc_18000E945
```
