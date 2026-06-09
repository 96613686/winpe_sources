# HTTP2ClientVirtualConnection::OpenReplacementOutChannel(void)

- ea: `0x1800106b8`
- end: `0x18001081e`
- name: `?OpenReplacementOutChannel@HTTP2ClientVirtualConnection@@QEAAJXZ`
- size: `358`
- prototype: `__int64 __fastcall(HTTP2ClientVirtualConnection *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180012110`

## callees

- `0x180003ffc`
- `0x180006050`
- `0x18000f2bc`
- `0x1800106b8`
- `0x18001ac1c`
- `0x18001bddc`
- `0x180025010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001075c`
- `ntdll!RtlLeaveCriticalSection` at `0x180010776`
- `ntdll!RtlLeaveCriticalSection` at `0x18001075c`
- `ntdll!RtlLeaveCriticalSection` at `0x180010776`
- `ntdll!RtlEnterCriticalSection` at `0x18001074a`
- `ntdll!RtlEnterCriticalSection` at `0x18001074a`

## pseudocode

```c
__int64 __fastcall HTTP2ClientVirtualConnection::OpenReplacementOutChannel(HTTP2ClientVirtualConnection *this)
{
  __int64 result; // rax
  __int64 v3; // rdx
  __int64 v4; // rsi
  HTTP2ChannelPointer *v5; // rdi
  struct HTTP2Channel *v6; // r14
  unsigned int v7; // edi
  struct _RTL_CRITICAL_SECTION *v8; // rcx
  __int64 v9; // rdx
  struct HTTP2SendContext *v10; // rax
  __int64 v11; // rdx
  struct HTTP2SendContext *v12; // rbp
  unsigned int v13; // esi
  __int64 v14; // rdx

  result = HTTP2ClientVirtualConnection::ClientOpenInternal(
             this,
             (HTTP2ClientVirtualConnection *)((char *)this + 448),
             1,
             *((_DWORD *)this + 94),
             0x2BF20u,
             0,
             1u,
             1u,
             1);
  if ( !(_DWORD)result )
  {
    v4 = 16 * (*((int *)this + 68) ^ 1LL);
    v5 = (HTTP2ClientVirtualConnection *)((char *)this + v4 + 200);
    v6 = HTTP2ChannelPointer::LockChannelPointer(v5, v3);
    if ( !v6 )
    {
LABEL_3:
      v7 = -1073606638;
LABEL_4:
      HTTP2ClientVirtualConnection::AbortChannels(this, v7);
      return v7;
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)this + 7);
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 280);
    if ( *((_DWORD *)this + 92) != 2 )
    {
      RtlLeaveCriticalSection(v8);
      HTTP2ChannelPointer::UnlockChannelPointer((HTTP2ClientVirtualConnection *)((char *)this + v4 + 200), v9);
      goto LABEL_3;
    }
    *((_DWORD *)this + 92) = 5;
    RtlLeaveCriticalSection(v8);
    v10 = AllocateAndInitializeD4_A3(
            *((_DWORD *)this + 97),
            (HTTP2ClientVirtualConnection *)((char *)this + 88),
            (HTTP2ClientVirtualConnection *)((char *)this + 16 * *((int *)this + 68) + 240),
            (HTTP2ClientVirtualConnection *)((char *)this + v4 + 240),
            HTTP2ClientReceiveWindow);
    v12 = v10;
    if ( !v10 )
    {
      HTTP2ChannelPointer::UnlockChannelPointer((HTTP2ClientVirtualConnection *)((char *)this + v4 + 200), v11);
      v7 = 14;
      goto LABEL_4;
    }
    v13 = (*(__int64 (__fastcall **)(struct HTTP2Channel *, struct HTTP2SendContext *))(*(_QWORD *)v6 + 8LL))(v6, v10);
    HTTP2ChannelPointer::UnlockChannelPointer(v5, v14);
    if ( v13 )
    {
      (*((void (__fastcall **)(struct HTTP2SendContext *))pRuntimeImportTable + 1))(v12);
      HTTP2ClientVirtualConnection::AbortChannels(this, v13);
      return v13;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800106b8  mov     rax, rsp
0x1800106bb  push    rbx
0x1800106bc  push    rbp
0x1800106bd  push    rsi
0x1800106be  push    rdi
0x1800106bf  push    r14
0x1800106c1  sub     rsp, 50h
0x1800106c5  mov     r9d, [rcx+178h]; unsigned int
0x1800106cc  lea     rdx, [rcx+1C0h]; struct HTTPResolverHint *
0x1800106d3  mov     edi, 1
0x1800106d8  mov     rbx, rcx
0x1800106db  mov     [rax-38h], edi
0x1800106de  mov     r8d, edi; int
0x1800106e1  mov     [rax-40h], edi
0x1800106e4  mov     [rax-48h], edi
0x1800106e7  mov     dword ptr [rax-50h], 0
0x1800106ee  mov     dword ptr [rax-58h], 2BF20h
0x1800106f5  call    ?ClientOpenInternal@HTTP2ClientVirtualConnection@@AEAAJPEAVHTTPResolverHint@@HIKHHHH@Z; HTTP2ClientVirtualConnection::ClientOpenInternal(HTTPResolverHint *,int,uint,ulong,int,int,int,int)
0x1800106fa  test    eax, eax
0x1800106fc  jnz     loc_180010813
0x180010702  movsxd  rsi, dword ptr [rbx+110h]
0x180010709  xor     rsi, rdi
0x18001070c  lea     rdi, [rbx+0C8h]
0x180010713  shl     rsi, 4
0x180010717  add     rdi, rsi
0x18001071a  mov     rcx, rdi; this
0x18001071d  call    ?LockChannelPointer@HTTP2ChannelPointer@@QEAAPEAVHTTP2Channel@@XZ; HTTP2ChannelPointer::LockChannelPointer(void)
0x180010722  mov     r14, rax
0x180010725  test    rax, rax
0x180010728  jnz     short loc_180010740
0x18001072a  mov     edi, 0C0021012h
0x18001072f  mov     edx, edi; int
0x180010731  mov     rcx, rbx; this
0x180010734  call    ?AbortChannels@HTTP2ClientVirtualConnection@@QEAAXJ@Z; HTTP2ClientVirtualConnection::AbortChannels(long)
0x180010739  mov     eax, edi
0x18001073b  jmp     loc_180010813
0x180010740  lea     rbp, [rbx+118h]
0x180010747  mov     rcx, rbp; CriticalSection
0x18001074a  call    cs:__imp_RtlEnterCriticalSection
0x180010750  cmp     dword ptr [rbx+170h], 2
0x180010757  mov     rcx, rbp; CriticalSection
0x18001075a  jz      short loc_18001076C
0x18001075c  call    cs:__imp_RtlLeaveCriticalSection
0x180010762  mov     rcx, rdi; this
0x180010765  call    ?UnlockChannelPointer@HTTP2ChannelPointer@@QEAAXXZ; HTTP2ChannelPointer::UnlockChannelPointer(void)
0x18001076a  jmp     short loc_18001072A
0x18001076c  mov     dword ptr [rbx+170h], 5
0x180010776  call    cs:__imp_RtlLeaveCriticalSection
0x18001077c  movsxd  r8, dword ptr [rbx+110h]
0x180010783  lea     r9, [rbx+0F0h]
0x18001078a  mov     r10d, cs:?HTTP2ClientReceiveWindow@@3KA; ulong HTTP2ClientReceiveWindow
0x180010791  lea     rdx, [rbx+58h]; struct HTTP2Cookie *
0x180010795  mov     ecx, [rbx+184h]; unsigned int
0x18001079b  add     r8, 0Fh
0x18001079f  shl     r8, 4
0x1800107a3  add     r9, rsi; struct HTTP2Cookie *
0x1800107a6  add     r8, rbx; struct HTTP2Cookie *
0x1800107a9  mov     [rsp+78h+var_58], r10d; unsigned int
0x1800107ae  call    ?AllocateAndInitializeD4_A3@@YAPEAVHTTP2SendContext@@KPEAVHTTP2Cookie@@00K@Z; AllocateAndInitializeD4_A3(ulong,HTTP2Cookie *,HTTP2Cookie *,HTTP2Cookie *,ulong)
0x1800107b3  mov     rbp, rax
0x1800107b6  test    rax, rax
0x1800107b9  jnz     short loc_1800107CB
0x1800107bb  mov     rcx, rdi; this
0x1800107be  call    ?UnlockChannelPointer@HTTP2ChannelPointer@@QEAAXXZ; HTTP2ChannelPointer::UnlockChannelPointer(void)
0x1800107c3  lea     edi, [rbp+0Eh]
0x1800107c6  jmp     loc_18001072F
0x1800107cb  mov     rax, [r14]
0x1800107ce  mov     rdx, rbp
0x1800107d1  mov     rcx, r14
0x1800107d4  mov     rax, [rax+8]
0x1800107d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107dd  mov     esi, eax
0x1800107df  mov     rcx, rdi; this
0x1800107e2  test    eax, eax
0x1800107e4  jz      short loc_18001080C
0x1800107e6  call    ?UnlockChannelPointer@HTTP2ChannelPointer@@QEAAXXZ; HTTP2ChannelPointer::UnlockChannelPointer(void)
0x1800107eb  mov     rcx, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800107f2  mov     rax, [rcx+8]
0x1800107f6  mov     rcx, rbp
0x1800107f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107fe  mov     edx, esi; int
0x180010800  mov     rcx, rbx; this
0x180010803  call    ?AbortChannels@HTTP2ClientVirtualConnection@@QEAAXJ@Z; HTTP2ClientVirtualConnection::AbortChannels(long)
0x180010808  mov     eax, esi
0x18001080a  jmp     short loc_180010813
0x18001080c  call    ?UnlockChannelPointer@HTTP2ChannelPointer@@QEAAXXZ; HTTP2ChannelPointer::UnlockChannelPointer(void)
0x180010811  xor     eax, eax
0x180010813  add     rsp, 50h
0x180010817  pop     r14
0x180010819  pop     rdi
0x18001081a  pop     rsi
0x18001081b  pop     rbp
0x18001081c  pop     rbx
0x18001081d  retn
```
