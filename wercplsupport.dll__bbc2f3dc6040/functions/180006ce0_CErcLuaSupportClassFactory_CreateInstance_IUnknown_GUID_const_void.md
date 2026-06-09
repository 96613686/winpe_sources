# CErcLuaSupportClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180006ce0`
- end: `0x180006e4c`
- name: `?CreateInstance@CErcLuaSupportClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `364`
- prototype: `__int64 __fastcall(CErcLuaSupportClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001634`
- `0x180002850`
- `0x180006c9c`
- `0x180006ce0`
- `0x1800073d4`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CErcLuaSupportClassFactory::CreateInstance(
        CErcLuaSupportClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v7; // ebx
  CManagedObj *v8; // rax
  CManagedObj *v9; // rdi

  *a4 = 0;
  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_01f8fd716d603d43032f2a74c7bf788f_Traceguids);
    return (unsigned int)-2147221232;
  }
  else
  {
    v8 = (CManagedObj *)operator new(0x28u);
    v9 = v8;
    if ( v8 )
    {
      CManagedObj::CManagedObj(v8);
      *((_QWORD *)v9 + 4) = this;
      *(_QWORD *)v9 = &CErcLuaSupport::`vftable'{for `CManagedObj'};
      *((_QWORD *)v9 + 3) = &CErcLuaSupport::`vftable'{for `IErcLuaSupport'};
      (*(void (__fastcall **)(CErcLuaSupportClassFactory *))(*(_QWORD *)this + 8LL))(this);
      _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
      v7 = (**(__int64 (__fastcall ***)(CManagedObj *, const struct _GUID *, void **))v9)(v9, a3, a4);
      if ( v7 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_01f8fd716d603d43032f2a74c7bf788f_Traceguids);
        v7 = 0;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_01f8fd716d603d43032f2a74c7bf788f_Traceguids,
          (unsigned int)v7);
      }
      (*(void (__fastcall **)(CManagedObj *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_01f8fd716d603d43032f2a74c7bf788f_Traceguids);
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006ce0  push    rbx
0x180006ce2  push    rbp
0x180006ce3  push    rsi
0x180006ce4  push    rdi
0x180006ce5  sub     rsp, 28h
0x180006ce9  mov     qword ptr [r9], 0
0x180006cf0  mov     rbx, r9
0x180006cf3  mov     rbp, r8
0x180006cf6  mov     rsi, rcx
0x180006cf9  test    rdx, rdx
0x180006cfc  jz      short loc_180006D36
0x180006cfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d05  lea     rax, WPP_GLOBAL_Control
0x180006d0c  cmp     rcx, rax
0x180006d0f  jz      short loc_180006D2C
0x180006d11  test    byte ptr [rcx+1Ch], 1
0x180006d15  jz      short loc_180006D2C
0x180006d17  mov     rcx, [rcx+10h]
0x180006d1b  lea     r8, WPP_01f8fd716d603d43032f2a74c7bf788f_Traceguids
0x180006d22  mov     edx, 0Ah
0x180006d27  call    WPP_SF_
0x180006d2c  mov     ebx, 80040110h
0x180006d31  jmp     loc_180006E41
0x180006d36  mov     ecx, 28h ; '('; Size
0x180006d3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006d40  mov     rdi, rax
0x180006d43  test    rax, rax
0x180006d46  jz      loc_180006E0E
0x180006d4c  mov     rcx, rax; this
0x180006d4f  call    ??0CManagedObj@@QEAA@XZ; CManagedObj::CManagedObj(void)
0x180006d54  lea     rax, ??_7CErcLuaSupport@@6BCManagedObj@@@; const CErcLuaSupport::`vftable'{for `CManagedObj'}
0x180006d5b  mov     [rdi+20h], rsi
0x180006d5f  mov     [rdi], rax
0x180006d62  mov     rcx, rsi
0x180006d65  lea     rax, ??_7CErcLuaSupport@@6BIErcLuaSupport@@@; const CErcLuaSupport::`vftable'{for `IErcLuaSupport'}
0x180006d6c  mov     [rdi+18h], rax
0x180006d70  mov     rax, [rsi]
0x180006d73  mov     rax, [rax+8]
0x180006d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d7c  lock inc dword ptr [rdi+8]
0x180006d80  mov     rax, [rdi]
0x180006d83  mov     r8, rbx
0x180006d86  mov     rdx, rbp
0x180006d89  mov     rcx, rdi
0x180006d8c  mov     rax, [rax]
0x180006d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d94  mov     ebx, eax
0x180006d96  test    eax, eax
0x180006d98  jns     short loc_180006DCD
0x180006d9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006da1  lea     rax, WPP_GLOBAL_Control
0x180006da8  cmp     rcx, rax
0x180006dab  jz      short loc_180006DFD
0x180006dad  test    byte ptr [rcx+1Ch], 1
0x180006db1  jz      short loc_180006DFD
0x180006db3  mov     rcx, [rcx+10h]
0x180006db7  lea     r8, WPP_01f8fd716d603d43032f2a74c7bf788f_Traceguids
0x180006dbe  mov     edx, 0Ch
0x180006dc3  mov     r9d, ebx
0x180006dc6  call    WPP_SF_d
0x180006dcb  jmp     short loc_180006DFD
0x180006dcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180006dd4  lea     rax, WPP_GLOBAL_Control
0x180006ddb  cmp     rcx, rax
0x180006dde  jz      short loc_180006DFB
0x180006de0  test    byte ptr [rcx+1Ch], 4
0x180006de4  jz      short loc_180006DFB
0x180006de6  mov     rcx, [rcx+10h]
0x180006dea  lea     r8, WPP_01f8fd716d603d43032f2a74c7bf788f_Traceguids
0x180006df1  mov     edx, 0Dh
0x180006df6  call    WPP_SF_
0x180006dfb  xor     ebx, ebx
0x180006dfd  mov     rax, [rdi]
0x180006e00  mov     rcx, rdi
0x180006e03  mov     rax, [rax+10h]
0x180006e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e0c  jmp     short loc_180006E41
0x180006e0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e15  lea     rax, WPP_GLOBAL_Control
0x180006e1c  cmp     rcx, rax
0x180006e1f  jz      short loc_180006E3C
0x180006e21  test    byte ptr [rcx+1Ch], 1
0x180006e25  jz      short loc_180006E3C
0x180006e27  mov     rcx, [rcx+10h]
0x180006e2b  lea     r8, WPP_01f8fd716d603d43032f2a74c7bf788f_Traceguids
0x180006e32  mov     edx, 0Bh
0x180006e37  call    WPP_SF_
0x180006e3c  mov     ebx, 8007000Eh
0x180006e41  mov     eax, ebx
0x180006e43  add     rsp, 28h
0x180006e47  pop     rdi
0x180006e48  pop     rsi
0x180006e49  pop     rbp
0x180006e4a  pop     rbx
0x180006e4b  retn
```
