# SpScsiReadCapacity(SP_DEVICE *,_IRP *)

- ea: `0x140034cc0`
- end: `0x140034e95`
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
- `0x140034cc0`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140034d8b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140034e73`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140034d8b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140034e73`

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
0x140034cc0  mov     rax, rsp
0x140034cc3  mov     [rax+8], rbx
0x140034cc7  mov     [rax+18h], rbp
0x140034ccb  push    rsi
0x140034ccc  push    rdi
0x140034ccd  push    r14
0x140034ccf  sub     rsp, 30h
0x140034cd3  mov     dword ptr [rax+10h], 0
0x140034cda  mov     rbp, rdx
0x140034cdd  mov     qword ptr [rax+10h], 0
0x140034ce5  mov     rsi, rcx
0x140034ce8  mov     rax, [rdx+0B8h]
0x140034cef  mov     rdi, [rax+8]
0x140034cf3  call    ?AcquireRundownShared@SP_DEVICE@@QEAAJPEAU_IRP@@@Z; SP_DEVICE::AcquireRundownShared(_IRP *)
0x140034cf8  mov     ebx, eax
0x140034cfa  test    eax, eax
0x140034cfc  jnz     loc_140034E7F
0x140034d02  cmp     byte ptr [rdi+48h], 25h ; '%'
0x140034d06  jnz     short loc_140034D1C
0x140034d08  cmp     dword ptr [rdi+10h], 8
0x140034d0c  jnb     loc_140034DA5
0x140034d12  mov     ebx, 0C0000023h
0x140034d17  jmp     loc_140034E6C
0x140034d1c  mov     al, [rdi+49h]
0x140034d1f  cmp     al, 10h
0x140034d21  jz      short loc_140034D9C
0x140034d23  cmp     al, 12h
0x140034d25  jz      short loc_140034D31
0x140034d27  mov     ebx, 0C0000002h
0x140034d2c  jmp     loc_140034E6C
0x140034d31  mov     rax, [rbp+0B8h]
0x140034d38  mov     rdx, rbp; struct _IRP *
0x140034d3b  mov     rcx, rsi; this
0x140034d3e  mov     rdi, [rax+8]
0x140034d42  call    ?AcquireRundownShared@SP_DEVICE@@QEAAJPEAU_IRP@@@Z; SP_DEVICE::AcquireRundownShared(_IRP *)
0x140034d47  mov     ebx, eax
0x140034d49  test    eax, eax
0x140034d4b  jnz     loc_140034E6C
0x140034d51  mov     rcx, [rsi+0C98h]; this
0x140034d58  lea     r9, [rdi+10h]; unsigned int *
0x140034d5c  mov     rdx, [rdi+4Ah]
0x140034d60  mov     r8, [rsi+0C58h]; unsigned __int64
0x140034d67  bswap   rdx
0x140034d6a  mov     eax, [rcx+84h]
0x140034d70  imul    rdx, rax; unsigned __int64
0x140034d74  mov     rax, [rdi+18h]
0x140034d78  mov     [rsp+48h+var_28], rax; void *
0x140034d7d  call    ?GetLbaStatus@SIO_SPACE@@QEAAJ_K0PEAKPEAX@Z; SIO_SPACE::GetLbaStatus(unsigned __int64,unsigned __int64,ulong *,void *)
0x140034d82  mov     ebx, eax
0x140034d84  mov     rcx, [rsi+0F0h]; RunRefCacheAware
0x140034d8b  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140034d92  nop     dword ptr [rax+rax+00h]
0x140034d97  jmp     loc_140034E6C
0x140034d9c  cmp     dword ptr [rdi+10h], 0Ch
0x140034da0  jmp     loc_140034D0C
0x140034da5  mov     r14, [rsi+0C98h]
0x140034dac  lea     rdx, [rsp+48h+arg_8]; void **
0x140034db1  mov     rcx, rbp; struct _IRP *
0x140034db4  call    ?SpGetSystemAddressFromSrb@@YAJPEAU_IRP@@PEAPEAX@Z; SpGetSystemAddressFromSrb(_IRP *,void * *)
0x140034db9  mov     ebx, eax
0x140034dbb  test    eax, eax
0x140034dbd  js      loc_140034E6C
0x140034dc3  mov     rax, [r14+70h]
0x140034dc7  mov     ecx, [r14+84h]
0x140034dce  cqo
0x140034dd0  idiv    rcx
0x140034dd3  dec     rax
0x140034dd6  cmp     byte ptr [rdi+48h], 25h ; '%'
0x140034dda  jnz     short loc_140034DFC
0x140034ddc  mov     rcx, [rsp+48h+arg_8]
0x140034de1  mov     dword ptr [rcx], 0FFFFFFFFh
0x140034de7  mov     eax, [r14+84h]
0x140034dee  bswap   eax
0x140034df0  mov     [rcx+4], eax
0x140034df3  mov     dword ptr [rdi+10h], 8
0x140034dfa  jmp     short loc_140034E6C
0x140034dfc  mov     r8, [rsp+48h+arg_8]
0x140034e01  bswap   rax
0x140034e04  mov     [r8], rax
0x140034e07  mov     eax, [r14+84h]
0x140034e0e  bswap   eax
0x140034e10  mov     [r8+8], eax
0x140034e14  cmp     dword ptr [rdi+10h], 20h ; ' '
0x140034e18  jnz     short loc_140034E65
0x140034e1a  and     byte ptr [r8+0Ch], 0FEh
0x140034e1f  xor     edx, edx
0x140034e21  mov     eax, [r14+88h]
0x140034e28  div     dword ptr [r14+84h]
0x140034e2f  bsf     ecx, eax
0x140034e32  mov     al, [r8+0Dh]
0x140034e36  and     cl, 0Fh
0x140034e39  and     al, 0F0h
0x140034e3b  or      al, cl
0x140034e3d  lea     rcx, [r8+0Eh]
0x140034e41  mov     [r8+0Dh], al
0x140034e45  cmp     byte ptr [rsi+0C28h], 0
0x140034e4c  jz      short loc_140034E51
0x140034e4e  or      byte ptr [rcx], 80h
0x140034e51  or      byte ptr [rcx], 40h
0x140034e54  and     byte ptr [rcx], 0C0h
0x140034e57  mov     byte ptr [r8+0Fh], 0
0x140034e5c  mov     dword ptr [rdi+10h], 20h ; ' '
0x140034e63  jmp     short loc_140034E6C
0x140034e65  mov     dword ptr [rdi+10h], 0Ch
0x140034e6c  mov     rcx, [rsi+0F0h]; RunRefCacheAware
0x140034e73  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140034e7a  nop     dword ptr [rax+rax+00h]
0x140034e7f  mov     rbp, [rsp+48h+arg_10]
0x140034e84  mov     eax, ebx
0x140034e86  mov     rbx, [rsp+48h+arg_0]
0x140034e8b  add     rsp, 30h
0x140034e8f  pop     r14
0x140034e91  pop     rdi
0x140034e92  pop     rsi
0x140034e93  retn
```
