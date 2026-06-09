# CWMIStandardShell::Initialize(ushort *,int,CHandleMap *,int,ulong,IWbemServices *,IWbemServices *,IWbemObjectSink *,IWbemContext *)

- ea: `0x180006bb0`
- end: `0x180006d44`
- name: `?Initialize@CWMIStandardShell@@QEAAJPEAGHPEAVCHandleMap@@HKPEAUIWbemServices@@2PEAUIWbemObjectSink@@PEAUIWbemContext@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(CWMIProcessClass **this, unsigned __int16 *, int, struct CHandleMap *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005048`
- `0x1800066b4`

## callees

- `0x180006bb0`
- `0x180006d4c`
- `0x180006d90`
- `0x180006e8c`
- `0x18000a0bc`
- `0x18001bc74`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180006bf6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180006cdb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180006bf6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180006cdb`

## pseudocode

```c
__int64 __fastcall CWMIStandardShell::Initialize(
        CWMIProcessClass **this,
        unsigned __int16 *a2,
        int a3,
        struct CHandleMap *a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v6; // r14
  CWMIProcessClass **v7; // rsi
  int v8; // edi
  _DWORD *v9; // r12
  _DWORD *v10; // rax
  _QWORD *v11; // rdx
  CWMIProcessClass *v12; // rcx
  CProcessStandardDataBlock *v13; // rax
  CProcessStandardDataBlock *v14; // rax
  char *v19; // [rsp+78h] [rbp+20h]

  v5 = a3;
  v6 = a2;
  v7 = this;
  v8 = -2147217407;
  v9 = this + 2;
  v19 = (char *)(this + 2);
  if ( !*((_DWORD *)this + 4) )
  {
    try
    {
      v10 = CWin32DefaultArena::WbemMemAlloc(0x68u);
      if ( v10 )
      {
        *(_QWORD *)v10 = 0;
        v10[21] = 0;
        v10[20] = 1;
        *((_QWORD *)v10 + 6) = 0;
        *((_QWORD *)v10 + 4) = 0;
        *((_QWORD *)v10 + 3) = 0;
        *((_QWORD *)v10 + 5) = 0;
        *((_QWORD *)v10 + 1) = 0;
        *((_QWORD *)v10 + 2) = 0;
        *((_WORD *)v10 + 36) = 0;
        v10[22] = 1;
        v10[23] = 1;
      }
      else
      {
        v10 = 0;
      }
      *v7 = (CWMIProcessClass *)v10;
    }
    catch ( ... )
    {
      *this = 0;
      v7 = this;
      v5 = a3;
      v6 = a2;
      v9 = v19;
    }
    if ( !*v7 )
      return (unsigned int)-2147217402;
    v8 = CWMIProcessClass::Initialize(*v7);
    if ( !v8 )
    {
      v11 = *(_QWORD **)*v7;
      v11[4] = 0;
      v11[1] = 0;
      v11[2] = 0;
      *v11 = 0;
      v11[3] = 0;
      *((_DWORD *)*v7 + 19) = 0;
      if ( !v6 )
        goto LABEL_17;
      v12 = *v7;
      if ( v5 )
      {
        v8 = CWMIProcessClass::SetClassName(v12, v6);
      }
      else
      {
        v8 = CWMIProcessClass::SetClass(v12, v6);
        if ( v8 >= 0 && (!*((_QWORD *)*v7 + 3) || !*((_QWORD *)*v7 + 1)) )
          v8 = -2147217393;
      }
      if ( !v8 )
      {
LABEL_17:
        v13 = (CProcessStandardDataBlock *)CWin32DefaultArena::WbemMemAlloc(0x4A8u);
        if ( v13 )
          v14 = CProcessStandardDataBlock::CProcessStandardDataBlock(v13);
        else
          v14 = 0;
        v7[1] = v14;
        if ( v14 )
        {
          *((_DWORD *)v14 + 293) = 1;
          CWMIDataBlock::SetClassProcessPtr(v7[1], *v7);
          *((_DWORD *)v7[1] + 2) = a5;
          *v9 = 1;
          return (unsigned int)v8;
        }
        return (unsigned int)-2147217402;
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006bb0  mov     rax, rsp
0x180006bb3  mov     [rax+20h], r9
0x180006bb7  mov     [rax+18h], r8d
0x180006bbb  mov     [rax+10h], rdx
0x180006bbf  mov     [rax+8], rcx
0x180006bc3  push    rbx
0x180006bc4  push    rsi
0x180006bc5  push    rdi
0x180006bc6  push    r12
0x180006bc8  push    r14
0x180006bca  push    r15
0x180006bcc  sub     rsp, 28h
0x180006bd0  mov     r15d, r8d
0x180006bd3  mov     r14, rdx
0x180006bd6  mov     rsi, rcx
0x180006bd9  mov     edi, 80041001h
0x180006bde  lea     r12, [rcx+10h]
0x180006be2  mov     [rsp+58h+arg_18], r12
0x180006be7  xor     ebx, ebx
0x180006be9  cmp     [r12], ebx
0x180006bed  jnz     loc_180006D34
0x180006bf3  lea     ecx, [rbx+68h]
0x180006bf6  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180006bfc  mov     [rsp+58h+arg_30], rax
0x180006c04  test    rax, rax
0x180006c07  jz      short loc_180006C42
0x180006c09  mov     [rax], rbx
0x180006c0c  mov     [rax+54h], ebx
0x180006c0f  mov     dword ptr [rax+50h], 1
0x180006c16  mov     [rax+30h], rbx
0x180006c1a  mov     [rax+20h], rbx
0x180006c1e  mov     [rax+18h], rbx
0x180006c22  mov     [rax+28h], rbx
0x180006c26  mov     [rax+8], rbx
0x180006c2a  mov     [rax+10h], rbx
0x180006c2e  mov     [rax+48h], bx
0x180006c32  mov     dword ptr [rax+58h], 1
0x180006c39  mov     dword ptr [rax+5Ch], 1
0x180006c40  jmp     short loc_180006C45
0x180006c42  mov     rax, rbx
0x180006c45  mov     [rsi], rax
0x180006c48  jmp     short loc_180006C60
0x180006c4a  xor     ebx, ebx
0x180006c4c  mov     rsi, [rsp+58h+arg_0]
0x180006c51  mov     r15d, [rsp+58h+arg_10]
0x180006c56  mov     r14, [rsp+58h+arg_8]
0x180006c5b  mov     r12, [rsp+58h+arg_18]
0x180006c60  cmp     [rsi], rbx
0x180006c63  jz      loc_180006D2F
0x180006c69  mov     rcx, [rsi]; this
0x180006c6c  call    ?Initialize@CWMIProcessClass@@QEAAJXZ; CWMIProcessClass::Initialize(void)
0x180006c71  mov     edi, eax
0x180006c73  test    eax, eax
0x180006c75  jnz     loc_180006D34
0x180006c7b  mov     rcx, [rsi]
0x180006c7e  mov     rdx, [rcx]
0x180006c81  mov     [rdx+20h], rbx
0x180006c85  mov     [rdx+8], rbx
0x180006c89  mov     [rdx+10h], rbx
0x180006c8d  mov     [rdx], rbx
0x180006c90  mov     [rdx+18h], rbx
0x180006c94  mov     rcx, [rsi]
0x180006c97  mov     [rcx+4Ch], ebx
0x180006c9a  test    r14, r14
0x180006c9d  jz      short loc_180006CD6
0x180006c9f  mov     rdx, r14; unsigned __int16 *
0x180006ca2  mov     rcx, [rsi]; this
0x180006ca5  test    r15d, r15d
0x180006ca8  jnz     short loc_180006CCB
0x180006caa  call    ?SetClass@CWMIProcessClass@@QEAAJPEAG@Z; CWMIProcessClass::SetClass(ushort *)
0x180006caf  mov     edi, eax
0x180006cb1  test    eax, eax
0x180006cb3  js      short loc_180006CD2
0x180006cb5  mov     rax, [rsi]
0x180006cb8  cmp     [rax+18h], rbx
0x180006cbc  jz      short loc_180006CC4
0x180006cbe  cmp     [rax+8], rbx
0x180006cc2  jnz     short loc_180006CD2
0x180006cc4  mov     edi, 8004100Fh
0x180006cc9  jmp     short loc_180006CD2
0x180006ccb  call    ?SetClassName@CWMIProcessClass@@QEAAJPEAG@Z; CWMIProcessClass::SetClassName(ushort *)
0x180006cd0  mov     edi, eax
0x180006cd2  test    edi, edi
0x180006cd4  jnz     short loc_180006D34
0x180006cd6  mov     ecx, 4A8h
0x180006cdb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180006ce1  mov     [rsp+58h+arg_0], rax
0x180006ce6  test    rax, rax
0x180006ce9  jz      short loc_180006CF5
0x180006ceb  mov     rcx, rax; this
0x180006cee  call    ??0CProcessStandardDataBlock@@QEAA@XZ; CProcessStandardDataBlock::CProcessStandardDataBlock(void)
0x180006cf3  jmp     short loc_180006CF8
0x180006cf5  mov     rax, rbx
0x180006cf8  mov     [rsi+8], rax
0x180006cfc  test    rax, rax
0x180006cff  jz      short loc_180006D2F
0x180006d01  mov     dword ptr [rax+494h], 1
0x180006d0b  mov     rdx, [rsi]; struct CWMIProcessClass *
0x180006d0e  mov     rcx, [rsi+8]; this
0x180006d12  call    ?SetClassProcessPtr@CWMIDataBlock@@QEAAXPEAVCWMIProcessClass@@@Z; CWMIDataBlock::SetClassProcessPtr(CWMIProcessClass *)
0x180006d17  mov     rcx, [rsi+8]
0x180006d1b  mov     eax, [rsp+58h+arg_20]
0x180006d22  mov     [rcx+8], eax
0x180006d25  mov     dword ptr [r12], 1
0x180006d2d  jmp     short loc_180006D34
0x180006d2f  mov     edi, 80041006h
0x180006d34  mov     eax, edi
0x180006d36  add     rsp, 28h
0x180006d3a  pop     r15
0x180006d3c  pop     r14
0x180006d3e  pop     r12
0x180006d40  pop     rdi
0x180006d41  pop     rsi
0x180006d42  pop     rbx
0x180006d43  retn
```
