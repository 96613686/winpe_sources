# WinHvpAllocatingHypercall

- ea: `0x140001ef0`
- end: `0x14000222b`
- name: `WinHvpAllocatingHypercall`
- size: `827`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, size_t Size, void *, size_t)`
- caller_count: `25`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140006f90`
- `0x1400085c0`
- `0x14001b010`
- `0x14001c280`
- `0x14001c310`
- `0x14001c3d0`
- `0x14001c7f0`
- `0x14001c850`
- `0x14001c9c0`
- `0x14001d900`
- `0x14001dce0`
- `0x14001f1c0`
- `0x14001fbb0`
- `0x1400215c0`
- `0x140021620`
- `0x1400236fc`
- `0x140023890`
- `0x140023970`
- `0x140023a20`
- `0x1400243d0`
- `0x140024570`
- `0x140025ed0`
- `0x140026070`
- `0x1400261c0`
- `0x140026670`

## callees

- `0x140001ef0`
- `0x140002240`
- `0x140002358`
- `0x1400024d0`
- `0x140002bf0`
- `0x1400048f0`
- `0x140004b1c`
- `0x140007d70`
- `0x140007da4`
- `0x140009c90`
- `0x140009d40`
- `0x14000a040`
- `0x14001b350`

## import_xrefs

- `ntoskrnl!HvlInvokeHypercall` at `0x140002013`
- `ntoskrnl!HvlInvokeHypercall` at `0x140002013`

## pseudocode

```c
__int64 __fastcall WinHvpAllocatingHypercall(
        __int64 a1,
        unsigned int a2,
        int a3,
        char a4,
        void *Src,
        size_t Size,
        void *a7,
        size_t a8)
{
  signed int v8; // ebx
  __int64 v11; // rsi
  __int64 *v12; // r14
  void **v13; // r15
  __int64 v14; // r8
  __int64 v15; // rdx
  unsigned __int16 v16; // ax
  int v18; // [rsp+30h] [rbp-98h]
  void *v19; // [rsp+38h] [rbp-90h] BYREF
  void *v20; // [rsp+40h] [rbp-88h] BYREF
  _QWORD v21[8]; // [rsp+50h] [rbp-78h] BYREF
  int v22; // [rsp+D0h] [rbp+8h]
  int v24; // [rsp+E8h] [rbp+20h]

  v22 = a1;
  v8 = 0;
  if ( a4 )
  {
    v11 = WinHvpReferencePartition(a1);
    if ( !v11 )
      return 3224698893LL;
  }
  else
  {
    v11 = 0;
  }
  v12 = (__int64 *)&v20;
  if ( !a7 )
    v12 = 0;
  v18 = 0;
  v24 = 0;
  v13 = &v19;
  if ( !Src )
    v13 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v19 = 0;
      v20 = 0;
      memset(v21, 0, sizeof(v21));
      WinHvpSetupHypercall((__int64 **)v13, v12, (__int64)v21);
      if ( Src )
        memmove(v19, Src, Size);
      if ( a4 )
        WinHvpAcquireAsyncMessage(v11);
      if ( *(_BYTE *)(v21[0] + 24LL) )
      {
        v8 = WinHvpSlowHypercallRemote(a3, 0, *(_QWORD *)(v21[0] + 8LL), *(_QWORD *)(v21[0] + 16LL), 0);
      }
      else
      {
        v14 = *(_QWORD *)(v21[0] + 16LL) ? *(_QWORD *)(*(_QWORD *)(v21[0] + 40LL) + 40LL) : 0LL;
        v15 = *(_QWORD *)(v21[0] + 8LL) ? *(_QWORD *)(*(_QWORD *)(v21[0] + 40LL) + 24LL) : 0LL;
        if ( WinHvpConnected )
        {
          v16 = HvlInvokeHypercall(-(__int64)(WinHvpNested != 0) & 0x80000000LL | (unsigned __int16)a3, v15, v14);
          if ( v16 )
            v8 = v16 | 0xC0350000;
        }
        else
        {
          v8 = -1070264320;
        }
      }
      if ( a7 && v8 >= 0 )
      {
        memmove(a7, v20, a8);
        ((void (__fastcall *)(_QWORD))v21[7])(v21[0]);
      }
      else
      {
        ((void (__fastcall *)(_QWORD))v21[7])(v21[0]);
        if ( v8 == -1070268295 && v11 )
          v8 = WinHvpWaitForAsyncCall(v11, 0, 0);
      }
      if ( a4 )
        WinHvpReleaseAsyncMessage(v11);
      if ( v8 != -1070268405 && v8 != -1070268299 && (unsigned int)(v8 + 1070268287) > 1 )
        break;
      v8 = WinHvpLowMemoryHandler(v22, a2, v8, a3, v18, v21[3]);
      if ( v8 < 0 )
        goto LABEL_28;
      ++v18;
      v8 = 0;
    }
    if ( v8 != -1070268301 && (unsigned int)(v8 + 1070268285) > 2 )
      break;
    v8 = WinHvLowMemoryPolicyAutoDeposit(0, -1, a2, (unsigned int)v8, a3, v24);
    if ( v8 < 0 )
      break;
    ++v24;
    v8 = 0;
  }
LABEL_28:
  if ( v11 )
    WinHvpDereferencePartition(v11);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140001ef0  mov     [rsp+arg_8], edx
0x140001ef4  mov     [rsp+arg_0], rcx
0x140001ef9  push    rbx
0x140001efa  push    rsi
0x140001efb  push    rdi
0x140001efc  push    r13
0x140001efe  sub     rsp, 0A8h
0x140001f05  xor     ebx, ebx
0x140001f07  mov     r13d, r8d
0x140001f0a  movzx   edi, r9b
0x140001f0e  test    r9b, r9b
0x140001f11  jnz     loc_1400021B1
0x140001f17  mov     esi, ebx
0x140001f19  mov     [rsp+0C8h+arg_10], rbp
0x140001f21  mov     rbp, [rsp+0C8h+Src]
0x140001f29  mov     [rsp+0C8h+var_28], r12
0x140001f31  mov     r12, [rsp+0C8h+arg_30]
0x140001f39  mov     [rsp+0C8h+var_30], r14
0x140001f41  test    r12, r12
0x140001f44  mov     [rsp+0C8h+var_38], r15
0x140001f4c  lea     r14, [rsp+0C8h+var_88]
0x140001f51  cmovz   r14, rbx
0x140001f55  mov     [rsp+0C8h+var_98], ebx
0x140001f59  test    rbp, rbp
0x140001f5c  mov     [rsp+0C8h+arg_18], ebx
0x140001f63  lea     r15, [rsp+0C8h+var_90]
0x140001f68  cmovz   r15, rbx
0x140001f6c  xor     edx, edx; Val
0x140001f6e  mov     [rsp+0C8h+var_90], rbx
0x140001f73  mov     r8d, 40h ; '@'; Size
0x140001f79  mov     [rsp+0C8h+var_88], rbx
0x140001f7e  lea     rcx, [rsp+0C8h+var_78]; void *
0x140001f83  call    memset
0x140001f88  lea     r8, [rsp+0C8h+var_78]
0x140001f8d  mov     rdx, r14
0x140001f90  mov     rcx, r15
0x140001f93  call    WinHvpSetupHypercall
0x140001f98  test    rbp, rbp
0x140001f9b  jz      short loc_140001FB2
0x140001f9d  mov     r8, [rsp+0C8h+Size]; Size
0x140001fa5  mov     rdx, rbp; Src
0x140001fa8  mov     rcx, [rsp+0C8h+var_90]; void *
0x140001fad  call    memmove
0x140001fb2  test    dil, dil
0x140001fb5  jnz     loc_1400021D5
0x140001fbb  mov     rax, [rsp+0C8h+var_78]
0x140001fc0  cmp     byte ptr [rax+18h], 0
0x140001fc4  jnz     loc_140002110
0x140001fca  cmp     qword ptr [rax+10h], 0
0x140001fcf  jnz     loc_1400020C7
0x140001fd5  mov     r8, rbx
0x140001fd8  cmp     qword ptr [rax+8], 0
0x140001fdd  jz      loc_1400021E2
0x140001fe3  mov     rdx, [rax+28h]
0x140001fe7  mov     rdx, [rdx+18h]
0x140001feb  movzx   eax, cs:WinHvpNested
0x140001ff2  neg     al
0x140001ff4  mov     eax, 80000000h
0x140001ff9  sbb     r9, r9
0x140001ffc  and     r9, rax
0x140001fff  cmp     cs:WinHvpConnected, 0
0x140002006  jz      loc_1400021EA
0x14000200c  movzx   ecx, r13w
0x140002010  or      rcx, r9
0x140002013  call    cs:__imp_HvlInvokeHypercall
0x14000201a  nop     dword ptr [rax+rax+00h]
0x14000201f  test    ax, ax
0x140002022  jnz     loc_14000212E
0x140002028  test    r12, r12
0x14000202b  jnz     loc_14000217D
0x140002031  mov     rcx, [rsp+0C8h+var_78]
0x140002036  mov     rax, [rsp+0C8h+var_40]
0x14000203e  call    _guard_dispatch_icall
0x140002043  cmp     ebx, 0C0350079h
0x140002049  jz      loc_1400021F4
0x14000204f  test    dil, dil
0x140002052  jnz     loc_140002211
0x140002058  cmp     ebx, 0C035000Bh
0x14000205e  jz      short loc_1400020D4
0x140002060  cmp     ebx, 0C0350075h
0x140002066  jz      short loc_1400020D4
0x140002068  lea     eax, [rbx+3FCAFF7Fh]
0x14000206e  cmp     eax, 1
0x140002071  jbe     short loc_1400020D4
0x140002073  cmp     ebx, 0C0350073h
0x140002079  jz      loc_14000213C
0x14000207f  lea     eax, [rbx+3FCAFF7Dh]
0x140002085  cmp     eax, 2
0x140002088  jbe     loc_14000213C
0x14000208e  mov     r15, [rsp+0C8h+var_38]
0x140002096  mov     r14, [rsp+0C8h+var_30]
0x14000209e  mov     r12, [rsp+0C8h+var_28]
0x1400020a6  mov     rbp, [rsp+0C8h+arg_10]
0x1400020ae  test    rsi, rsi
0x1400020b1  jnz     loc_14000221E
0x1400020b7  mov     eax, ebx
0x1400020b9  add     rsp, 0A8h
0x1400020c0  pop     r13
0x1400020c2  pop     rdi
0x1400020c3  pop     rsi
0x1400020c4  pop     rbx
0x1400020c5  retn
0x1400020c7  mov     r8, [rax+28h]
0x1400020cb  mov     r8, [r8+28h]
0x1400020cf  jmp     loc_140001FD8
0x1400020d4  movzx   eax, [rsp+0C8h+var_60]
0x1400020d9  mov     r9d, r13d
0x1400020dc  mov     edx, [rsp+0C8h+arg_8]
0x1400020e3  mov     r8d, ebx
0x1400020e6  mov     rcx, [rsp+0C8h+arg_0]
0x1400020ee  mov     byte ptr [rsp+0C8h+var_A0], al
0x1400020f2  mov     eax, [rsp+0C8h+var_98]
0x1400020f6  mov     dword ptr [rsp+0C8h+var_A8], eax
0x1400020fa  call    WinHvpLowMemoryHandler
0x1400020ff  mov     ebx, eax
0x140002101  test    eax, eax
0x140002103  js      short loc_14000208E
0x140002105  inc     [rsp+0C8h+var_98]
0x140002109  xor     ebx, ebx
0x14000210b  jmp     loc_140001F6C
0x140002110  mov     r9, [rax+10h]
0x140002114  xor     edx, edx
0x140002116  mov     r8, [rax+8]
0x14000211a  mov     ecx, r13d
0x14000211d  mov     [rsp+0C8h+var_A8], rbx
0x140002122  call    WinHvpSlowHypercallRemote
0x140002127  mov     ebx, eax
0x140002129  jmp     loc_140002028
0x14000212e  movzx   ebx, ax
0x140002131  or      ebx, 0C0350000h
0x140002137  jmp     loc_140002028
0x14000213c  mov     eax, [rsp+0C8h+arg_18]
0x140002143  mov     r9d, ebx
0x140002146  mov     r8d, [rsp+0C8h+arg_8]
0x14000214e  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x140002155  mov     [rsp+0C8h+var_A0], eax
0x140002159  xor     ecx, ecx
0x14000215b  mov     dword ptr [rsp+0C8h+var_A8], r13d
0x140002160  call    WinHvLowMemoryPolicyAutoDeposit
0x140002165  mov     ebx, eax
0x140002167  test    eax, eax
0x140002169  js      loc_14000208E
0x14000216f  inc     [rsp+0C8h+arg_18]
0x140002176  xor     ebx, ebx
0x140002178  jmp     loc_140001F6C
0x14000217d  test    ebx, ebx
0x14000217f  js      loc_140002031
0x140002185  mov     r8, [rsp+0C8h+arg_38]; Size
0x14000218d  mov     rcx, r12; void *
0x140002190  mov     rdx, [rsp+0C8h+var_88]; Src
0x140002195  call    memmove
0x14000219a  mov     rcx, [rsp+0C8h+var_78]
0x14000219f  mov     rax, [rsp+0C8h+var_40]
0x1400021a7  call    _guard_dispatch_icall
0x1400021ac  jmp     loc_14000204F
0x1400021b1  call    WinHvpReferencePartition
0x1400021b6  mov     rsi, rax
0x1400021b9  test    rax, rax
0x1400021bc  jnz     loc_140001F19
0x1400021c2  mov     eax, 0C035000Dh
0x1400021c7  add     rsp, 0A8h
0x1400021ce  pop     r13
0x1400021d0  pop     rdi
0x1400021d1  pop     rsi
0x1400021d2  pop     rbx
0x1400021d3  retn
0x1400021d5  mov     rcx, rsi
0x1400021d8  call    WinHvpAcquireAsyncMessage
0x1400021dd  jmp     loc_140001FBB
0x1400021e2  mov     rdx, rbx
0x1400021e5  jmp     loc_140001FEB
0x1400021ea  mov     ebx, 0C0351000h
0x1400021ef  jmp     loc_140002028
0x1400021f4  test    rsi, rsi
0x1400021f7  jz      loc_14000204F
0x1400021fd  xor     r8d, r8d
0x140002200  xor     edx, edx
0x140002202  mov     rcx, rsi
0x140002205  call    WinHvpWaitForAsyncCall
0x14000220a  mov     ebx, eax
0x14000220c  jmp     loc_14000204F
0x140002211  mov     rcx, rsi
0x140002214  call    WinHvpReleaseAsyncMessage
0x140002219  jmp     loc_140002058
0x14000221e  mov     rcx, rsi
0x140002221  call    WinHvpDereferencePartition
0x140002226  jmp     loc_1400020B7
```
