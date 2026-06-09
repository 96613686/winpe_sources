# VidExoBrokerIoctlReceive

- ea: `0x140077d7c`
- end: `0x140077fbd`
- name: `VidExoBrokerIoctlReceive`
- size: `577`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140037fd0`

## callees

- `0x140021d40`
- `0x140023e40`
- `0x140023ee8`
- `0x140024754`
- `0x140038630`
- `0x140077d7c`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x140077e4a`
- `ntoskrnl!IoGetRequestorProcess` at `0x140077e4a`
- `ntoskrnl!ObDuplicateObject` at `0x140077eb8`
- `ntoskrnl!ObDuplicateObject` at `0x140077eb8`
- `ntoskrnl!IofCompleteRequest` at `0x140077f39`
- `ntoskrnl!IofCompleteRequest` at `0x140077f39`
- `ntoskrnl!ZwClose` at `0x140077ee3`
- `ntoskrnl!ZwClose` at `0x140077ee3`
- `ntoskrnl!PsGetCurrentProcess` at `0x140077e5e`
- `ntoskrnl!PsGetCurrentProcess` at `0x140077e5e`

## string_xrefs

- `0x140077db5`: `VidExoBrokerIoctlReceive`
- `0x140077f00`: `VidExoBrokerIoctlReceive`
- `0x140077f66`: `VidExoBrokerIoctlReceive`
- `0x140077f9d`: `VidExoBrokerIoctlReceive`
- `0x140077dae`: `onecore\vm\vid\sys\driver\videxobroker.c`
- `0x140077ef9`: `onecore\vm\vid\sys\driver\videxobroker.c`
- `0x140077f5f`: `onecore\vm\vid\sys\driver\videxobroker.c`
- `0x140077f96`: `onecore\vm\vid\sys\driver\videxobroker.c`

## pseudocode

```c
__int64 __fastcall VidExoBrokerIoctlReceive(
        __int64 a1,
        __int64 a2,
        unsigned int *a3,
        unsigned int a4,
        unsigned int *a5)
{
  __int64 v8; // rax
  IRP *v9; // rbp
  int v10; // ebx
  __int64 v11; // r8
  unsigned int *v12; // rsi
  unsigned __int64 v13; // rax
  unsigned int v14; // ecx
  unsigned int v15; // r15d
  PEPROCESS RequestorProcess; // rbx
  __int64 CurrentProcess; // rcx
  char *v18; // r12
  char *v19; // rax
  __int64 v20; // rdi
  int v22; // [rsp+38h] [rbp-70h]
  char *v23; // [rsp+40h] [rbp-68h]
  struct _KPROCESS *v24; // [rsp+48h] [rbp-60h]
  __int64 v25; // [rsp+50h] [rbp-58h]

  v8 = VidExoBrokerpFindAndDequeueSendIrpForFileObject();
  v9 = (IRP *)v8;
  if ( !v8 )
  {
    v10 = -1073741811;
    VidTraceErrorInternal0("VidExoBrokerIoctlReceive", "onecore\\vm\\vid\\sys\\driver\\videxobroker.c", 186);
LABEL_23:
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VidExoBrokerIoctlReceive",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\videxobroker.c",
      316,
      v10,
      a1 + 656);
    return (unsigned int)v10;
  }
  if ( a4 < 0x10 )
  {
    v10 = -1073741306;
    v11 = 199;
LABEL_21:
    VidTraceErrorInternal0("VidExoBrokerIoctlReceive", "onecore\\vm\\vid\\sys\\driver\\videxobroker.c", v11);
    VidExoBrokerpQueueSendIrp(a1, v9);
    goto LABEL_22;
  }
  v12 = *(unsigned int **)(v8 + 24);
  *a3 = 16;
  a3[1] = v12[1];
  v13 = 8LL * v12[1];
  if ( v13 > 0xFFFFFFFF || (v14 = v13 + 16, (unsigned int)(v13 + 16) < 0x10) )
  {
    v10 = -1073741306;
    v11 = 211;
    goto LABEL_21;
  }
  a3[2] = v14;
  a3[3] = v12[3];
  v15 = v14 + v12[3];
  if ( v15 < v14 )
  {
    v10 = -1073741306;
    v11 = 221;
    goto LABEL_21;
  }
  if ( a4 < v15 )
  {
    v10 = -2147483643;
    *a5 = 16;
    v11 = 243;
    goto LABEL_21;
  }
  RequestorProcess = IoGetRequestorProcess(v9);
  v24 = RequestorProcess;
  CurrentProcess = PsGetCurrentProcess();
  v25 = CurrentProcess;
  v18 = (char *)a3 + *a3;
  v19 = (char *)v12 + *v12;
  v23 = v19;
  v20 = 0;
  while ( 1 )
  {
    if ( (unsigned int)v20 >= v12[1] )
    {
      memmove((char *)a3 + a3[2], (char *)v12 + v12[2], v12[3]);
      v10 = 0;
      *a5 = v15;
      goto LABEL_18;
    }
    LOBYTE(v22) = 1;
    v10 = ObDuplicateObject(RequestorProcess, *(_QWORD *)&v19[8 * v20], CurrentProcess, &v18[8 * v20], 0, 0, 10, v22);
    if ( v10 < 0 )
      break;
    v19 = v23;
    v20 = (unsigned int)(v20 + 1);
    RequestorProcess = v24;
    CurrentProcess = v25;
  }
  while ( (_DWORD)v20 )
  {
    LODWORD(v20) = v20 - 1;
    ZwClose(*(HANDLE *)&v18[8 * (unsigned int)v20]);
  }
  VidTraceErrorInternal0("VidExoBrokerIoctlReceive", "onecore\\vm\\vid\\sys\\driver\\videxobroker.c", 282);
LABEL_18:
  v9->IoStatus.Status = v10;
  IofCompleteRequest(v9, 0);
LABEL_22:
  if ( v10 < 0 )
    goto LABEL_23;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140077d7c  push    rbx
0x140077d7e  push    rbp
0x140077d7f  push    rsi
0x140077d80  push    rdi
0x140077d81  push    r12
0x140077d83  push    r13
0x140077d85  push    r14
0x140077d87  push    r15
0x140077d89  sub     rsp, 68h
0x140077d8d  mov     ebx, r9d
0x140077d90  mov     r14, r8
0x140077d93  mov     r13, rcx
0x140077d96  call    VidExoBrokerpFindAndDequeueSendIrpForFileObject
0x140077d9b  mov     rbp, rax
0x140077d9e  test    rax, rax
0x140077da1  jnz     short loc_140077DC6
0x140077da3  mov     ebx, 0C000000Dh
0x140077da8  mov     r8d, 0BAh
0x140077dae  lea     rdx, aOnecoreVmVidSy_53; "onecore\\vm\\vid\\sys\\driver\\videxobr"...
0x140077db5  lea     rcx, aVidexobrokerio; "VidExoBrokerIoctlReceive"
0x140077dbc  call    VidTraceErrorInternal0
0x140077dc1  jmp     loc_140077F81
0x140077dc6  mov     edx, 10h
0x140077dcb  cmp     ebx, edx
0x140077dcd  jnb     short loc_140077DDF
0x140077dcf  mov     ebx, 0C0000206h
0x140077dd4  mov     r8d, 0C7h
0x140077dda  jmp     loc_140077F5F
0x140077ddf  mov     rsi, [rax+18h]
0x140077de3  mov     ecx, 0FFFFFFFFh
0x140077de8  mov     [r14], edx
0x140077deb  mov     eax, [rsi+4]
0x140077dee  mov     [r14+4], eax
0x140077df2  mov     eax, [rsi+4]
0x140077df5  shl     rax, 3
0x140077df9  cmp     rax, rcx
0x140077dfc  ja      loc_140077F54
0x140077e02  lea     ecx, [rax+10h]
0x140077e05  cmp     ecx, edx
0x140077e07  jb      loc_140077F54
0x140077e0d  mov     [r14+8], ecx
0x140077e11  mov     eax, [rsi+0Ch]
0x140077e14  mov     [r14+0Ch], eax
0x140077e18  mov     r15d, [rsi+0Ch]
0x140077e1c  add     r15d, ecx
0x140077e1f  cmp     r15d, ecx
0x140077e22  jb      loc_140077F47
0x140077e28  cmp     ebx, r15d
0x140077e2b  jnb     short loc_140077E47
0x140077e2d  mov     rax, [rsp+0A8h+arg_20]
0x140077e35  mov     ebx, 80000005h
0x140077e3a  mov     [rax], edx
0x140077e3c  mov     r8d, 0F3h
0x140077e42  jmp     loc_140077F5F
0x140077e47  mov     rcx, rbp; Irp
0x140077e4a  call    cs:__imp_IoGetRequestorProcess
0x140077e51  nop     dword ptr [rax+rax+00h]
0x140077e56  mov     rbx, rax
0x140077e59  mov     [rsp+0A8h+var_60], rax
0x140077e5e  call    cs:__imp_PsGetCurrentProcess
0x140077e65  nop     dword ptr [rax+rax+00h]
0x140077e6a  mov     r12d, [r14]
0x140077e6d  mov     rcx, rax
0x140077e70  mov     [rsp+0A8h+var_58], rax
0x140077e75  add     r12, r14
0x140077e78  mov     eax, [rsi]
0x140077e7a  add     rax, rsi
0x140077e7d  mov     [rsp+0A8h+var_68], rax
0x140077e82  xor     edi, edi
0x140077e84  cmp     edi, [rsi+4]
0x140077e87  jnb     loc_140077F0E
0x140077e8d  mov     rdx, [rax+rdi*8]
0x140077e91  lea     r9, [r12+rdi*8]
0x140077e95  mov     [rsp+0A8h+var_70], 1
0x140077e9a  mov     r8, rcx
0x140077e9d  mov     [rsp+0A8h+var_78], 0Ah
0x140077ea5  mov     rcx, rbx
0x140077ea8  mov     [rsp+0A8h+var_80], 0
0x140077eb0  mov     dword ptr [rsp+0A8h+var_88], 0
0x140077eb8  call    cs:__imp_ObDuplicateObject
0x140077ebf  nop     dword ptr [rax+rax+00h]
0x140077ec4  mov     ebx, eax
0x140077ec6  test    eax, eax
0x140077ec8  js      short loc_140077EEF
0x140077eca  mov     rax, [rsp+0A8h+var_68]
0x140077ecf  inc     edi
0x140077ed1  mov     rbx, [rsp+0A8h+var_60]
0x140077ed6  mov     rcx, [rsp+0A8h+var_58]
0x140077edb  jmp     short loc_140077E84
0x140077edd  dec     edi
0x140077edf  mov     rcx, [r12+rdi*8]; Handle
0x140077ee3  call    cs:__imp_ZwClose
0x140077eea  nop     dword ptr [rax+rax+00h]
0x140077eef  test    edi, edi
0x140077ef1  jnz     short loc_140077EDD
0x140077ef3  mov     r8d, 11Ah
0x140077ef9  lea     rdx, aOnecoreVmVidSy_53; "onecore\\vm\\vid\\sys\\driver\\videxobr"...
0x140077f00  lea     rcx, aVidexobrokerio; "VidExoBrokerIoctlReceive"
0x140077f07  call    VidTraceErrorInternal0
0x140077f0c  jmp     short loc_140077F31
0x140077f0e  mov     edx, [rsi+8]
0x140077f11  mov     ecx, [r14+8]
0x140077f15  add     rdx, rsi; Src
0x140077f18  mov     r8d, [rsi+0Ch]; Size
0x140077f1c  add     rcx, r14; void *
0x140077f1f  call    memmove
0x140077f24  mov     rax, [rsp+0A8h+arg_20]
0x140077f2c  xor     ebx, ebx
0x140077f2e  mov     [rax], r15d
0x140077f31  xor     edx, edx; PriorityBoost
0x140077f33  mov     [rbp+30h], ebx
0x140077f36  mov     rcx, rbp; Irp
0x140077f39  call    cs:__imp_IofCompleteRequest
0x140077f40  nop     dword ptr [rax+rax+00h]
0x140077f45  jmp     short loc_140077F7D
0x140077f47  mov     ebx, 0C0000206h
0x140077f4c  mov     r8d, 0DDh
0x140077f52  jmp     short loc_140077F5F
0x140077f54  mov     ebx, 0C0000206h
0x140077f59  mov     r8d, 0D3h
0x140077f5f  lea     rdx, aOnecoreVmVidSy_53; "onecore\\vm\\vid\\sys\\driver\\videxobr"...
0x140077f66  lea     rcx, aVidexobrokerio; "VidExoBrokerIoctlReceive"
0x140077f6d  call    VidTraceErrorInternal0
0x140077f72  mov     rdx, rbp
0x140077f75  mov     rcx, r13
0x140077f78  call    VidExoBrokerpQueueSendIrp
0x140077f7d  test    ebx, ebx
0x140077f7f  jns     short loc_140077FA9
0x140077f81  lea     rax, [r13+290h]
0x140077f88  mov     r9d, ebx
0x140077f8b  mov     r8d, 13Ch
0x140077f91  mov     [rsp+0A8h+var_88], rax
0x140077f96  lea     rdx, aOnecoreVmVidSy_53; "onecore\\vm\\vid\\sys\\driver\\videxobr"...
0x140077f9d  lea     rcx, aVidexobrokerio; "VidExoBrokerIoctlReceive"
0x140077fa4  call    VidTraceErrorStatusPartitionInternal0
0x140077fa9  mov     eax, ebx
0x140077fab  add     rsp, 68h
0x140077faf  pop     r15
0x140077fb1  pop     r14
0x140077fb3  pop     r13
0x140077fb5  pop     r12
0x140077fb7  pop     rdi
0x140077fb8  pop     rsi
0x140077fb9  pop     rbp
0x140077fba  pop     rbx
0x140077fbb  retn
```
