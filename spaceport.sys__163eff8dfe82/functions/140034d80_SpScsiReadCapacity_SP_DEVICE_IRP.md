# SpScsiReadCapacity(SP_DEVICE *,_IRP *)

- ea: `0x140034d80`
- end: `0x140034f55`
- name: `?SpScsiReadCapacity@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(struct SP_DEVICE *this, struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001e230`

## callees

- `0x1400108f0`
- `0x1400184c0`
- `0x140026a00`
- `0x140034d80`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140034e4b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140034f33`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140034e4b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140034f33`

## pseudocode

```c
__int64 __fastcall SpScsiReadCapacity(struct SP_DEVICE *this, struct _IRP *a2)
{
  PIO_SECURITY_CONTEXT SecurityContext; // rdi
  int LbaStatus; // ebx
  bool v6; // cf
  char v7; // al
  PIO_SECURITY_CONTEXT v8; // rdi
  __int64 v9; // r14
  _DWORD *v10; // rcx
  char *v11; // r8
  unsigned int v12; // ecx
  char v13; // al
  _BYTE *v14; // rcx
  void *v16; // [rsp+58h] [rbp+10h] BYREF

  v16 = 0;
  SecurityContext = a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  LbaStatus = SP_DEVICE::AcquireRundownShared(this, a2);
  if ( !LbaStatus )
  {
    if ( LOBYTE(SecurityContext[3].SecurityQos) == 37 )
    {
      v6 = SecurityContext->DesiredAccess < 8;
    }
    else
    {
      v7 = BYTE1(SecurityContext[3].SecurityQos);
      if ( v7 != 16 )
      {
        if ( v7 == 18 )
        {
          v8 = a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
          LbaStatus = SP_DEVICE::AcquireRundownShared(this, a2);
          if ( !LbaStatus )
          {
            LbaStatus = SIO_SPACE::GetLbaStatus(
                          *((SIO_SPACE **)this + 403),
                          *(unsigned int *)(*((_QWORD *)this + 403) + 132LL)
                        * _byteswap_uint64(*(unsigned __int64 *)((char *)&v8[3].SecurityQos + 2)),
                          *((_QWORD *)this + 395),
                          &v8->DesiredAccess,
                          v8[1].SecurityQos);
            ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)this + 30));
          }
        }
        else
        {
          LbaStatus = -1073741822;
        }
        goto LABEL_20;
      }
      v6 = SecurityContext->DesiredAccess < 0xC;
    }
    if ( v6 )
    {
      LbaStatus = -1073741789;
    }
    else
    {
      v9 = *((_QWORD *)this + 403);
      LbaStatus = SpGetSystemAddressFromSrb(a2, &v16);
      if ( LbaStatus >= 0 )
      {
        if ( LOBYTE(SecurityContext[3].SecurityQos) == 37 )
        {
          v10 = v16;
          *(_DWORD *)v16 = -1;
          v10[1] = _byteswap_ulong(*(_DWORD *)(v9 + 132));
          SecurityContext->DesiredAccess = 8;
        }
        else
        {
          v11 = (char *)v16;
          *(_QWORD *)v16 = _byteswap_uint64(*(_QWORD *)(v9 + 112) / (__int64)*(unsigned int *)(v9 + 132) - 1);
          *((_DWORD *)v11 + 2) = _byteswap_ulong(*(_DWORD *)(v9 + 132));
          if ( SecurityContext->DesiredAccess == 32 )
          {
            v11[12] &= ~1u;
            _BitScanForward(&v12, *(_DWORD *)(v9 + 136) / *(_DWORD *)(v9 + 132));
            v13 = v12 & 0xF | v11[13] & 0xF0;
            v14 = v11 + 14;
            v11[13] = v13;
            if ( *((_BYTE *)this + 3112) )
              *v14 |= 0x80u;
            *v14 |= 0x40u;
            *v14 &= 0xC0u;
            v11[15] = 0;
            SecurityContext->DesiredAccess = 32;
          }
          else
          {
            SecurityContext->DesiredAccess = 12;
          }
        }
      }
    }
LABEL_20:
    ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)this + 30));
  }
  return (unsigned int)LbaStatus;
}

```

## disassembly

```asm
0x140034d80  mov     rax, rsp
0x140034d83  mov     [rax+8], rbx
0x140034d87  mov     [rax+18h], rbp
0x140034d8b  push    rsi
0x140034d8c  push    rdi
0x140034d8d  push    r14
0x140034d8f  sub     rsp, 30h
0x140034d93  mov     dword ptr [rax+10h], 0
0x140034d9a  mov     rbp, rdx
0x140034d9d  mov     qword ptr [rax+10h], 0
0x140034da5  mov     rsi, rcx
0x140034da8  mov     rax, [rdx+0B8h]
0x140034daf  mov     rdi, [rax+8]
0x140034db3  call    ?AcquireRundownShared@SP_DEVICE@@QEAAJPEAU_IRP@@@Z; SP_DEVICE::AcquireRundownShared(_IRP *)
0x140034db8  mov     ebx, eax
0x140034dba  test    eax, eax
0x140034dbc  jnz     loc_140034F3F
0x140034dc2  cmp     byte ptr [rdi+48h], 25h ; '%'
0x140034dc6  jnz     short loc_140034DDC
0x140034dc8  cmp     dword ptr [rdi+10h], 8
0x140034dcc  jnb     loc_140034E65
0x140034dd2  mov     ebx, 0C0000023h
0x140034dd7  jmp     loc_140034F2C
0x140034ddc  mov     al, [rdi+49h]
0x140034ddf  cmp     al, 10h
0x140034de1  jz      short loc_140034E5C
0x140034de3  cmp     al, 12h
0x140034de5  jz      short loc_140034DF1
0x140034de7  mov     ebx, 0C0000002h
0x140034dec  jmp     loc_140034F2C
0x140034df1  mov     rax, [rbp+0B8h]
0x140034df8  mov     rdx, rbp; struct _IRP *
0x140034dfb  mov     rcx, rsi; this
0x140034dfe  mov     rdi, [rax+8]
0x140034e02  call    ?AcquireRundownShared@SP_DEVICE@@QEAAJPEAU_IRP@@@Z; SP_DEVICE::AcquireRundownShared(_IRP *)
0x140034e07  mov     ebx, eax
0x140034e09  test    eax, eax
0x140034e0b  jnz     loc_140034F2C
0x140034e11  mov     rcx, [rsi+0C98h]; this
0x140034e18  lea     r9, [rdi+10h]; unsigned int *
0x140034e1c  mov     rdx, [rdi+4Ah]
0x140034e20  mov     r8, [rsi+0C58h]; unsigned __int64
0x140034e27  bswap   rdx
0x140034e2a  mov     eax, [rcx+84h]
0x140034e30  imul    rdx, rax; unsigned __int64
0x140034e34  mov     rax, [rdi+18h]
0x140034e38  mov     [rsp+48h+var_28], rax; void *
0x140034e3d  call    ?GetLbaStatus@SIO_SPACE@@QEAAJ_K0PEAKPEAX@Z; SIO_SPACE::GetLbaStatus(unsigned __int64,unsigned __int64,ulong *,void *)
0x140034e42  mov     ebx, eax
0x140034e44  mov     rcx, [rsi+0F0h]; RunRefCacheAware
0x140034e4b  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140034e52  nop     dword ptr [rax+rax+00h]
0x140034e57  jmp     loc_140034F2C
0x140034e5c  cmp     dword ptr [rdi+10h], 0Ch
0x140034e60  jmp     loc_140034DCC
0x140034e65  mov     r14, [rsi+0C98h]
0x140034e6c  lea     rdx, [rsp+48h+arg_8]; void **
0x140034e71  mov     rcx, rbp; struct _IRP *
0x140034e74  call    ?SpGetSystemAddressFromSrb@@YAJPEAU_IRP@@PEAPEAX@Z; SpGetSystemAddressFromSrb(_IRP *,void * *)
0x140034e79  mov     ebx, eax
0x140034e7b  test    eax, eax
0x140034e7d  js      loc_140034F2C
0x140034e83  mov     rax, [r14+70h]
0x140034e87  mov     ecx, [r14+84h]
0x140034e8e  cqo
0x140034e90  idiv    rcx
0x140034e93  dec     rax
0x140034e96  cmp     byte ptr [rdi+48h], 25h ; '%'
0x140034e9a  jnz     short loc_140034EBC
0x140034e9c  mov     rcx, [rsp+48h+arg_8]
0x140034ea1  mov     dword ptr [rcx], 0FFFFFFFFh
0x140034ea7  mov     eax, [r14+84h]
0x140034eae  bswap   eax
0x140034eb0  mov     [rcx+4], eax
0x140034eb3  mov     dword ptr [rdi+10h], 8
0x140034eba  jmp     short loc_140034F2C
0x140034ebc  mov     r8, [rsp+48h+arg_8]
0x140034ec1  bswap   rax
0x140034ec4  mov     [r8], rax
0x140034ec7  mov     eax, [r14+84h]
0x140034ece  bswap   eax
0x140034ed0  mov     [r8+8], eax
0x140034ed4  cmp     dword ptr [rdi+10h], 20h ; ' '
0x140034ed8  jnz     short loc_140034F25
0x140034eda  and     byte ptr [r8+0Ch], 0FEh
0x140034edf  xor     edx, edx
0x140034ee1  mov     eax, [r14+88h]
0x140034ee8  div     dword ptr [r14+84h]
0x140034eef  bsf     ecx, eax
0x140034ef2  mov     al, [r8+0Dh]
0x140034ef6  and     cl, 0Fh
0x140034ef9  and     al, 0F0h
0x140034efb  or      al, cl
0x140034efd  lea     rcx, [r8+0Eh]
0x140034f01  mov     [r8+0Dh], al
0x140034f05  cmp     byte ptr [rsi+0C28h], 0
0x140034f0c  jz      short loc_140034F11
0x140034f0e  or      byte ptr [rcx], 80h
0x140034f11  or      byte ptr [rcx], 40h
0x140034f14  and     byte ptr [rcx], 0C0h
0x140034f17  mov     byte ptr [r8+0Fh], 0
0x140034f1c  mov     dword ptr [rdi+10h], 20h ; ' '
0x140034f23  jmp     short loc_140034F2C
0x140034f25  mov     dword ptr [rdi+10h], 0Ch
0x140034f2c  mov     rcx, [rsi+0F0h]; RunRefCacheAware
0x140034f33  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140034f3a  nop     dword ptr [rax+rax+00h]
0x140034f3f  mov     rbp, [rsp+48h+arg_10]
0x140034f44  mov     eax, ebx
0x140034f46  mov     rbx, [rsp+48h+arg_0]
0x140034f4b  add     rsp, 30h
0x140034f4f  pop     r14
0x140034f51  pop     rdi
0x140034f52  pop     rsi
0x140034f53  retn
```
