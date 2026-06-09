# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180007d4c`
- end: `0x180007df1`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *this, int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800082a0`
- `0x18001a7a0`

## callees

- `0x180007d4c`
- `0x18000c1d4`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007d96`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007d96`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007dcd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007dcd`

## pseudocode

```c
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this, int a2, unsigned int a3)
{
  unsigned __int64 v3; // r14
  __int64 v5; // rsi
  _QWORD *v6; // r15
  _QWORD *v7; // rbx
  __int64 v8; // rcx

  v3 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v5 = v3 & -(__int64)(this != 0);
      if ( !v5 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC0000005LL, a2, a3);
        JUMPOUT(0x180007DF0LL);
      }
      v6 = *(_QWORD **)((v3 & -(__int64)(this != 0)) + 8);
      if ( v6 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v6)(v6[1]);
          v7 = (_QWORD *)v6[2];
          operator delete(v6);
          v6 = v7;
        }
        while ( v7 );
      }
      *(_QWORD *)(v5 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v8 = *((_QWORD *)this + 8);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v3 = 0;
  }
}

```

## disassembly

```asm
0x180007d4c  push    rbx
0x180007d4e  push    rsi
0x180007d4f  push    rdi
0x180007d50  push    r14
0x180007d52  push    r15
0x180007d54  sub     rsp, 20h
0x180007d58  lea     r14, [rcx+8]
0x180007d5c  mov     rdi, rcx
0x180007d5f  cmp     dword ptr [r14], 0
0x180007d63  jz      short loc_180007DDA
0x180007d65  cmp     qword ptr [rcx+10h], 0
0x180007d6a  jz      short loc_180007DB4
0x180007d6c  mov     rax, rcx
0x180007d6f  neg     rax
0x180007d72  sbb     rsi, rsi
0x180007d75  and     rsi, r14
0x180007d78  jz      short loc_180007DE6
0x180007d7a  mov     r15, [rsi+8]
0x180007d7e  test    r15, r15
0x180007d81  jz      short loc_180007DA4
0x180007d83  mov     rcx, [r15+8]
0x180007d87  mov     rax, [r15]
0x180007d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d8f  mov     rbx, [r15+10h]
0x180007d93  mov     rcx, r15
0x180007d96  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007d9c  mov     r15, rbx
0x180007d9f  test    rbx, rbx
0x180007da2  jnz     short loc_180007D83
0x180007da4  mov     qword ptr [rsi+8], 0
0x180007dac  mov     qword ptr [rdi+10h], 0
0x180007db4  mov     rcx, [rdi+40h]
0x180007db8  test    rcx, rcx
0x180007dbb  jz      short loc_180007DC9
0x180007dbd  mov     rax, [rcx]
0x180007dc0  mov     rax, [rax+10h]
0x180007dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dc9  lea     rcx, [rdi+18h]; lpCriticalSection
0x180007dcd  call    cs:__imp_DeleteCriticalSection
0x180007dd3  mov     dword ptr [r14], 0
0x180007dda  add     rsp, 20h
0x180007dde  pop     r15
0x180007de0  pop     r14
0x180007de2  pop     rdi
0x180007de3  pop     rsi
0x180007de4  pop     rbx
0x180007de5  retn
0x180007de6  mov     ecx, 0C0000005h; this
0x180007deb  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
