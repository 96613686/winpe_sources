# VMX_CONFIG::SynchronizeConfigCopy(VMX_CONFIG_COPY *)

- ea: `0x140041d3c`
- end: `0x140041f8a`
- name: `?SynchronizeConfigCopy@VMX_CONFIG@@QEAAJPEAVVMX_CONFIG_COPY@@@Z`
- size: `590`
- prototype: `__int64 __fastcall(VMX_CONFIG *__hidden this, struct VMX_CONFIG_COPY *)`
- caller_count: `6`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002b13c`
- `0x14002c3dc`
- `0x14002caf8`
- `0x14002dcb0`
- `0x140039028`
- `0x1400537c4`

## callees

- `0x140005f80`
- `0x140008d28`
- `0x1400099d8`
- `0x140040690`
- `0x140040880`
- `0x140041d3c`
- `0x1400587d4`
- `0x14005ab10`

## pseudocode

```c
__int64 __fastcall VMX_CONFIG::SynchronizeConfigCopy(VMX_CONFIG *this, struct VMX_CONFIG_COPY *a2)
{
  __int64 v4; // rsi
  __int64 v5; // rax
  __int64 v6; // r15
  __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  __int64 v10; // rax
  VMX_CONFIG *v11; // rax
  VMX_CONFIG *v12; // rdi
  unsigned int v13; // edx
  int v14; // ebp
  unsigned int v16; // edx
  VMX_RAW_CONFIG *v17; // rcx
  unsigned int v18; // ebx
  VMX_NOTIFICATION_QUEUE *v19; // rcx
  __int64 v20; // rdx

  v4 = 32;
  if ( !*((_BYTE *)a2 + 16) || *((_BYTE *)a2 + 18) )
    goto LABEL_29;
  v5 = *((_QWORD *)this + 1);
  v6 = 64;
  v7 = 64;
  if ( *(_WORD *)(v5 + 72) != 3 )
    v7 = 56;
  v8 = *(_QWORD *)(v7 + v5);
  v9 = v8 - 2;
  if ( v8 <= 2 )
    v9 = 0;
  v10 = 32;
  if ( *((_WORD *)a2 + 10) != 3 )
    v10 = 24;
  if ( *(_QWORD *)((char *)a2 + v10) < v9 )
    goto LABEL_29;
  v11 = (VMX_CONFIG *)VMX_ALLOCATED_OBJECT::operator new(0x38u, 0x102u, 0x6F436D56u);
  v12 = v11;
  if ( !v11 )
  {
    v19 = WPP_GLOBAL_Control;
    v18 = -1073741670;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v18;
    }
    v20 = 97;
    goto LABEL_42;
  }
  *(_QWORD *)v11 = 0;
  *((_QWORD *)v11 + 1) = 0;
  *((_QWORD *)v11 + 4) = 0;
  *((_QWORD *)v11 + 5) = 0;
  *((_QWORD *)v11 + 3) = (char *)v11 + 16;
  *((_QWORD *)v11 + 2) = (char *)v11 + 16;
  *((_QWORD *)v11 + 6) = 1;
  v14 = VMX_CONFIG::Read(v11, a2);
  if ( v14 >= 0 )
  {
    if ( *((_BYTE *)a2 + 17) || !*((_BYTE *)a2 + 19) )
    {
      VMX_CONFIG::`scalar deleting destructor'(v12, v13);
      v19 = WPP_GLOBAL_Control;
      v18 = -1070071806;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return v18;
      }
      v20 = 99;
      goto LABEL_42;
    }
    if ( VMX_CONFIG::SameAs(this, v12) )
    {
      VMX_CONFIG::`scalar deleting destructor'(v12, v16);
      v17 = (VMX_RAW_CONFIG *)*((_QWORD *)this + 1);
      if ( *((_WORD *)v17 + 36) != 3 )
        v6 = 56;
      if ( *((_WORD *)a2 + 10) != 3 )
        v4 = 24;
      if ( *(_QWORD *)((char *)a2 + v4) != *(_QWORD *)((char *)v17 + v6) )
        VMX_RAW_CONFIG::WriteHeader(v17, a2);
      return 0;
    }
    *((_BYTE *)a2 + 19) = 0;
    VMX_CONFIG::`scalar deleting destructor'(v12, v16);
LABEL_29:
    v18 = VMX_RAW_CONFIG::AtomicWrite(*((VMX_RAW_CONFIG **)this + 1), a2);
    if ( (v18 & 0x80000000) != 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return v18;
      }
      v20 = 100;
LABEL_42:
      WPP_SF_d(*((_QWORD *)v19 + 3), v20, WPP_ecea8329fd353f2ede86956965576228_Traceguids, v18);
      return v18;
    }
    return 0;
  }
  VMX_CONFIG::`scalar deleting destructor'(v12, v13);
  if ( !*((_BYTE *)a2 + 17) )
    goto LABEL_29;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      98,
      WPP_ecea8329fd353f2ede86956965576228_Traceguids,
      (unsigned int)v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140041d3c  push    rbx
0x140041d3e  push    rbp
0x140041d3f  push    rsi
0x140041d40  push    rdi
0x140041d41  push    r14
0x140041d43  push    r15
0x140041d45  sub     rsp, 28h
0x140041d49  cmp     byte ptr [rdx+10h], 0
0x140041d4d  mov     rbx, rdx
0x140041d50  mov     r14, rcx
0x140041d53  mov     esi, 20h ; ' '
0x140041d58  jz      loc_140041ECE
0x140041d5e  cmp     byte ptr [rdx+12h], 0
0x140041d62  jnz     loc_140041ECE
0x140041d68  mov     rax, [rcx+8]
0x140041d6c  lea     r15d, [rsi+20h]
0x140041d70  mov     ecx, r15d
0x140041d73  lea     r9d, [rsi+18h]
0x140041d77  cmp     word ptr [rax+48h], 3
0x140041d7c  cmovnz  ecx, r9d
0x140041d80  mov     rcx, [rcx+rax]
0x140041d84  xor     eax, eax
0x140041d86  cmp     rcx, 2
0x140041d8a  lea     rdx, [rcx-2]
0x140041d8e  cmovbe  rdx, rax
0x140041d92  lea     ecx, [rsi-8]
0x140041d95  cmp     word ptr [rbx+14h], 3
0x140041d9a  mov     eax, esi
0x140041d9c  cmovnz  eax, ecx
0x140041d9f  cmp     [rax+rbx], rdx
0x140041da3  jb      loc_140041ECE
0x140041da9  mov     edx, 102h; unsigned __int64
0x140041dae  mov     r8d, 6F436D56h; unsigned int
0x140041db4  mov     ecx, r9d; unsigned __int64
0x140041db7  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x140041dbc  mov     rdi, rax
0x140041dbf  test    rax, rax
0x140041dc2  jz      loc_140041F45
0x140041dc8  mov     qword ptr [rax], 0
0x140041dcf  lea     rcx, [rax+10h]
0x140041dd3  mov     qword ptr [rax+8], 0
0x140041ddb  mov     rdx, rbx; struct VMX_CONFIG_COPY *
0x140041dde  mov     qword ptr [rax+20h], 0
0x140041de6  mov     qword ptr [rax+28h], 0
0x140041dee  mov     [rcx+8], rcx
0x140041df2  mov     [rcx], rcx
0x140041df5  mov     rcx, rax; this
0x140041df8  mov     qword ptr [rax+30h], 1
0x140041e00  call    ?Read@VMX_CONFIG@@QEAAJPEAVVMX_CONFIG_COPY@@@Z; VMX_CONFIG::Read(VMX_CONFIG_COPY *)
0x140041e05  mov     ebp, eax
0x140041e07  test    eax, eax
0x140041e09  jns     short loc_140041E58
0x140041e0b  mov     rcx, rdi; this
0x140041e0e  call    ??_GVMX_CONFIG@@QEAAPEAXI@Z; VMX_CONFIG::`scalar deleting destructor'(uint)
0x140041e13  cmp     byte ptr [rbx+11h], 0
0x140041e17  jz      loc_140041ECE
0x140041e1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140041e24  lea     rdx, WPP_GLOBAL_Control
0x140041e2b  cmp     rcx, rdx
0x140041e2e  jz      short loc_140041E54
0x140041e30  mov     eax, [rcx+2Ch]
0x140041e33  test    sil, al
0x140041e36  jz      short loc_140041E54
0x140041e38  cmp     byte ptr [rcx+29h], 2
0x140041e3c  jb      short loc_140041E54
0x140041e3e  mov     rcx, [rcx+18h]
0x140041e42  lea     edx, [rsi+42h]
0x140041e45  mov     r9d, ebp
0x140041e48  lea     r8, WPP_ecea8329fd353f2ede86956965576228_Traceguids
0x140041e4f  call    WPP_SF_d
0x140041e54  mov     eax, ebp
0x140041e56  jmp     short loc_140041EB7
0x140041e58  cmp     byte ptr [rbx+11h], 0
0x140041e5c  jnz     loc_140041F10
0x140041e62  cmp     byte ptr [rbx+13h], 0
0x140041e66  jz      loc_140041F10
0x140041e6c  mov     rdx, rdi; struct VMX_CONFIG *
0x140041e6f  mov     rcx, r14; this
0x140041e72  call    ?SameAs@VMX_CONFIG@@AEAAEPEAV1@@Z; VMX_CONFIG::SameAs(VMX_CONFIG *)
0x140041e77  mov     rcx, rdi; this
0x140041e7a  test    al, al
0x140041e7c  jz      short loc_140041EC5
0x140041e7e  call    ??_GVMX_CONFIG@@QEAAPEAXI@Z; VMX_CONFIG::`scalar deleting destructor'(uint)
0x140041e83  mov     rcx, [r14+8]; this
0x140041e87  mov     eax, 38h ; '8'
0x140041e8c  cmp     word ptr [rcx+48h], 3
0x140041e91  cmovnz  r15, rax
0x140041e95  cmp     word ptr [rbx+14h], 3
0x140041e9a  mov     eax, 18h
0x140041e9f  cmovnz  rsi, rax
0x140041ea3  mov     rax, [r15+rcx]
0x140041ea7  cmp     [rsi+rbx], rax
0x140041eab  jz      short loc_140041EB5
0x140041ead  mov     rdx, rbx; struct VMX_CONFIG_COPY *
0x140041eb0  call    ?WriteHeader@VMX_RAW_CONFIG@@QEAAJPEAVVMX_CONFIG_COPY@@@Z; VMX_RAW_CONFIG::WriteHeader(VMX_CONFIG_COPY *)
0x140041eb5  xor     eax, eax
0x140041eb7  add     rsp, 28h
0x140041ebb  pop     r15
0x140041ebd  pop     r14
0x140041ebf  pop     rdi
0x140041ec0  pop     rsi
0x140041ec1  pop     rbp
0x140041ec2  pop     rbx
0x140041ec3  retn
0x140041ec5  mov     byte ptr [rbx+13h], 0
0x140041ec9  call    ??_GVMX_CONFIG@@QEAAPEAXI@Z; VMX_CONFIG::`scalar deleting destructor'(uint)
0x140041ece  mov     rcx, [r14+8]; this
0x140041ed2  mov     rdx, rbx; struct VMX_CONFIG_COPY *
0x140041ed5  call    ?AtomicWrite@VMX_RAW_CONFIG@@QEAAJPEAVVMX_CONFIG_COPY@@@Z; VMX_RAW_CONFIG::AtomicWrite(VMX_CONFIG_COPY *)
0x140041eda  mov     ebx, eax
0x140041edc  test    eax, eax
0x140041ede  jns     short loc_140041EB5
0x140041ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x140041ee7  lea     rdx, WPP_GLOBAL_Control
0x140041eee  cmp     rcx, rdx
0x140041ef1  jz      loc_140041F83
0x140041ef7  mov     edx, [rcx+2Ch]
0x140041efa  test    sil, dl
0x140041efd  jz      loc_140041F83
0x140041f03  cmp     byte ptr [rcx+29h], 2
0x140041f07  jb      short loc_140041F83
0x140041f09  mov     edx, 64h ; 'd'
0x140041f0e  jmp     short loc_140041F70
0x140041f10  mov     rcx, rdi; this
0x140041f13  call    ??_GVMX_CONFIG@@QEAAPEAXI@Z; VMX_CONFIG::`scalar deleting destructor'(uint)
0x140041f18  mov     rcx, cs:WPP_GLOBAL_Control
0x140041f1f  lea     rdx, WPP_GLOBAL_Control
0x140041f26  mov     ebx, 0C0380002h
0x140041f2b  cmp     rcx, rdx
0x140041f2e  jz      short loc_140041F83
0x140041f30  mov     edx, [rcx+2Ch]
0x140041f33  test    sil, dl
0x140041f36  jz      short loc_140041F83
0x140041f38  cmp     byte ptr [rcx+29h], 2
0x140041f3c  jb      short loc_140041F83
0x140041f3e  mov     edx, 63h ; 'c'
0x140041f43  jmp     short loc_140041F70
0x140041f45  mov     rcx, cs:WPP_GLOBAL_Control
0x140041f4c  lea     rdx, WPP_GLOBAL_Control
0x140041f53  mov     ebx, 0C000009Ah
0x140041f58  cmp     rcx, rdx
0x140041f5b  jz      short loc_140041F83
0x140041f5d  mov     edx, [rcx+2Ch]
0x140041f60  test    sil, dl
0x140041f63  jz      short loc_140041F83
0x140041f65  cmp     byte ptr [rcx+29h], 2
0x140041f69  jb      short loc_140041F83
0x140041f6b  mov     edx, 61h ; 'a'
0x140041f70  mov     rcx, [rcx+18h]
0x140041f74  lea     r8, WPP_ecea8329fd353f2ede86956965576228_Traceguids
0x140041f7b  mov     r9d, ebx
0x140041f7e  call    WPP_SF_d
0x140041f83  mov     eax, ebx
0x140041f85  jmp     loc_140041EB7
```
