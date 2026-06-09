# FlSetAllVirtualInterfaceParameters

- ea: `0x1401a9e40`
- end: `0x1401aa26a`
- name: `FlSetAllVirtualInterfaceParameters`
- size: `1066`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x1400fb124`
- `0x140103d74`
- `0x140103de4`
- `0x1401197e8`
- `0x14014a818`
- `0x1401a8018`
- `0x1401a8760`
- `0x1401a8a8c`
- `0x1401a8d24`
- `0x1401a9a88`
- `0x1401a9c30`
- `0x1401a9e40`
- `0x1401aa340`
- `0x1401aa4e8`
- `0x1401b4e38`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa111`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa19e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa111`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa19e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401aa105`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401aa192`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401aa105`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401aa192`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401aa041`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401aa041`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401aa02c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401aa02c`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a9f93`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a9fec`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a9f93`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a9fec`

## pseudocode

```c
__int64 __fastcall FlSetAllVirtualInterfaceParameters(__int64 *a1)
{
  __int64 v1; // rax
  __int64 v2; // r14
  __int64 v3; // r12
  int v5; // esi
  __int64 v6; // r15
  _DWORD *v7; // rbx
  int v8; // eax
  char *v9; // rdi
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  int v12; // r13d
  __int64 Interface; // rax
  __int64 v14; // r8
  int Compartment; // edi
  int v16; // eax
  __int64 v17; // r8
  _QWORD *ClientInterface; // r15
  __int64 v19; // rdx
  __int64 v20; // rcx
  char *v21; // rcx
  char v22; // cl
  int v23; // edx
  int v25; // [rsp+70h] [rbp-49h] BYREF
  unsigned int v26; // [rsp+74h] [rbp-45h] BYREF
  int v27; // [rsp+78h] [rbp-41h] BYREF
  __int64 v28; // [rsp+80h] [rbp-39h]
  __int64 v29; // [rsp+88h] [rbp-31h] BYREF
  __int64 v30; // [rsp+90h] [rbp-29h] BYREF
  char *v31; // [rsp+98h] [rbp-21h]
  __int128 v32; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v33; // [rsp+B0h] [rbp-9h] BYREF

  v1 = *a1;
  v2 = 0;
  v3 = a1[2];
  v30 = 0;
  v5 = 22;
  v6 = *(_QWORD *)(v1 + 40);
  v28 = v6;
  v25 = 22;
  v26 = 0;
  v33 = 0;
  v27 = 0;
  v32 = 0;
  if ( *((_DWORD *)a1 + 13)
    || (v7 = a1 + 6, v8 = *((_DWORD *)a1 + 12), v8 == 4)
    || !*(_DWORD *)(v3 + 24) && v8
    || (v9 = (char *)a1[4], v31 = v9, !v8) && !v9
    || (v10 = *(_DWORD *)(v3 + 28), v10 > 2) )
  {
    Compartment = -1073741811;
    v7 = a1 + 6;
    v5 = 0;
    goto LABEL_44;
  }
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( !v11 )
    {
      v12 = 3;
      goto LABEL_14;
    }
    if ( v11 == 1 )
    {
      v12 = 1;
      goto LABEL_14;
    }
  }
  v12 = 0;
LABEL_14:
  Interface = FlpFindInterface(v6 + 440, *(_QWORD *)v3, 0);
  v2 = Interface;
  if ( !Interface )
  {
    Compartment = -1073741275;
    v5 = 8;
    goto LABEL_44;
  }
  if ( *v7 )
  {
    if ( *v7 == 1 )
    {
      LOBYTE(v14) = 1;
      if ( (unsigned __int8)NetioIsCompartmentAccessibleByThread(
                              *(unsigned int *)(Interface + 1184),
                              Interface + 952,
                              v14) )
      {
        Compartment = FlIfFindCompartment(v3 + 8, &v26, &v33, &v32, 0);
        if ( Compartment >= 0 )
        {
          LOBYTE(v17) = 1;
          if ( (unsigned __int8)NetioIsCompartmentAccessibleByThread(v26, &v32, v17) )
          {
            ClientInterface = FlpCreateClientInterface(v2);
            if ( ClientInterface )
            {
              KeEnterCriticalRegion();
              ExAcquireResourceExclusiveLite(&Resource, 1u);
              if ( !FlIfpFindVirtualInterfaceUnderLock(*(_QWORD *)(v2 + 1168), *(unsigned int *)(v3 + 24)) )
              {
                v29 = 0;
                if ( (int)FlIfpQueryVirtualInterfaceLuid(v20, v19, &v29) >= 0 )
                {
                  InternalCleanupPersistentStore(2, &v29);
                  InternalCleanupPersistentStore(23, &v29);
                }
              }
              Compartment = FlIfCreateVirtualInterface(
                              v2,
                              (int)v3 + 8,
                              *(_DWORD *)(v3 + 24),
                              v12,
                              1,
                              0,
                              0,
                              v26,
                              (__int64)&v32,
                              (__int64)&v33,
                              *(_WORD *)(v28 + 92),
                              (__int64)&v30,
                              (__int64)&v27,
                              (__int64)&v25);
              if ( Compartment >= 0 )
              {
                v21 = v31;
                ClientInterface[11] = v30;
                *((_DWORD *)ClientInterface + 24) = v27;
                *((_DWORD *)ClientInterface + 26) = v26;
                *((_DWORD *)ClientInterface + 25) = *(_DWORD *)(v3 + 24);
                *((_DWORD *)ClientInterface + 32) = v12;
                *(_OWORD *)((char *)ClientInterface + 108) = FlIfIsolationTag;
                if ( v21 )
                {
                  v22 = *v21;
                  if ( v22 != -1 )
                    *((_BYTE *)ClientInterface + 64) ^= (*((_BYTE *)ClientInterface + 64) ^ (2 * v22)) & 2;
                }
                Compartment = FlpAddInterface((PRTL_DYNAMIC_HASH_TABLE_ENTRY)ClientInterface);
                ExReleaseResourceLite(&Resource);
                KeLeaveCriticalRegion();
                if ( Compartment >= 0 )
                  goto LABEL_47;
                v23 = *(_DWORD *)(v3 + 24);
                v5 = 19;
                v27 = 0;
                FlIfDeleteVirtualInterface(v2, v23, 1, *(unsigned __int16 *)(v28 + 92), (__int64)&v27);
                FlpDereferenceClientInterface(ClientInterface);
              }
              else
              {
                ExReleaseResourceLite(&Resource);
                KeLeaveCriticalRegion();
                FlpDereferenceClientInterface(ClientInterface);
                v5 = v25;
              }
            }
            else
            {
              Compartment = -1073741670;
              v5 = 1;
            }
            v6 = v28;
          }
          else
          {
            Compartment = -1073741275;
            v5 = 3;
          }
        }
        else
        {
          v5 = 6;
        }
      }
      else
      {
        Compartment = -1073741275;
        v5 = 4;
      }
      goto LABEL_44;
    }
    if ( *v7 != 3 )
    {
      Compartment = -1073741637;
      goto LABEL_44;
    }
    v16 = FlIfDeleteVirtualInterfaceHelper(
            Interface,
            *(_DWORD *)(v3 + 24),
            1,
            *(unsigned __int16 *)(v6 + 92),
            1,
            (__int64)&v25);
  }
  else
  {
    v16 = FlpSetVirtualInterfaceHelper(Interface, v3, v9, &v25);
  }
  Compartment = v16;
  if ( v16 >= 0 )
  {
LABEL_47:
    FlpDereferenceInterface(v2);
    return (unsigned int)Compartment;
  }
  v5 = v25;
LABEL_44:
  if ( SBYTE6(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
    FlpLogVirtualIfCtlError(*v7, *(unsigned __int16 *)(v6 + 92), v3, Compartment, v5, 1);
  if ( v2 )
    goto LABEL_47;
  return (unsigned int)Compartment;
}

```

## disassembly

```asm
0x1401a9e40  push    rbp
0x1401a9e42  push    rbx
0x1401a9e43  push    rsi
0x1401a9e44  push    rdi
0x1401a9e45  push    r12
0x1401a9e47  push    r13
0x1401a9e49  push    r14
0x1401a9e4b  push    r15
0x1401a9e4d  lea     rbp, [rsp-1Fh]
0x1401a9e52  sub     rsp, 0D8h
0x1401a9e59  mov     rax, cs:__security_cookie
0x1401a9e60  xor     rax, rsp
0x1401a9e63  mov     [rbp+57h+var_50], rax
0x1401a9e67  mov     rax, [rcx]
0x1401a9e6a  xor     r14d, r14d
0x1401a9e6d  xorps   xmm0, xmm0
0x1401a9e70  mov     r12, [rcx+10h]
0x1401a9e74  xorps   xmm1, xmm1
0x1401a9e77  mov     rdx, rcx
0x1401a9e7a  mov     [rbp+57h+var_80], r14
0x1401a9e7e  lea     esi, [r14+16h]
0x1401a9e82  mov     r15, [rax+28h]
0x1401a9e86  mov     [rbp+57h+var_90], r15
0x1401a9e8a  mov     [rbp+57h+var_A0], esi
0x1401a9e8d  mov     [rbp+57h+var_9C], r14d
0x1401a9e91  movups  [rbp+57h+var_60], xmm0
0x1401a9e95  mov     [rbp+57h+var_98], r14d
0x1401a9e99  movups  [rbp+57h+var_70], xmm1
0x1401a9e9d  cmp     [rcx+34h], r14d
0x1401a9ea1  jnz     loc_1401AA20B
0x1401a9ea7  lea     rbx, [rcx+30h]
0x1401a9eab  mov     eax, [rbx]
0x1401a9ead  cmp     eax, 4
0x1401a9eb0  jz      loc_1401AA20B
0x1401a9eb6  cmp     [r12+18h], r14d
0x1401a9ebb  jnz     short loc_1401A9EC5
0x1401a9ebd  test    eax, eax
0x1401a9ebf  jnz     loc_1401AA20B
0x1401a9ec5  mov     rdi, [rcx+20h]
0x1401a9ec9  mov     [rbp+57h+var_78], rdi
0x1401a9ecd  test    eax, eax
0x1401a9ecf  jnz     short loc_1401A9EDA
0x1401a9ed1  test    rdi, rdi
0x1401a9ed4  jz      loc_1401AA20B
0x1401a9eda  mov     ecx, [r12+1Ch]
0x1401a9edf  cmp     ecx, 2
0x1401a9ee2  ja      loc_1401AA20B
0x1401a9ee8  test    ecx, ecx
0x1401a9eea  jz      short loc_1401A9F03
0x1401a9eec  sub     ecx, 1
0x1401a9eef  jz      short loc_1401A9EFB
0x1401a9ef1  cmp     ecx, 1
0x1401a9ef4  jnz     short loc_1401A9F03
0x1401a9ef6  mov     r13d, ecx
0x1401a9ef9  jmp     short loc_1401A9F06
0x1401a9efb  mov     r13d, 3
0x1401a9f01  jmp     short loc_1401A9F06
0x1401a9f03  mov     r13d, r14d
0x1401a9f06  mov     rdx, [r12]
0x1401a9f0a  lea     rcx, [r15+1B8h]
0x1401a9f11  xor     r8d, r8d
0x1401a9f14  call    FlpFindInterface
0x1401a9f19  mov     r14, rax
0x1401a9f1c  test    rax, rax
0x1401a9f1f  jnz     short loc_1401A9F2E
0x1401a9f21  mov     edi, 0C0000225h
0x1401a9f26  lea     esi, [rax+8]
0x1401a9f29  jmp     loc_1401AA216
0x1401a9f2e  mov     ecx, [rbx]
0x1401a9f30  test    ecx, ecx
0x1401a9f32  jz      loc_1401AA1EE
0x1401a9f38  sub     ecx, 1
0x1401a9f3b  jz      short loc_1401A9F77
0x1401a9f3d  cmp     ecx, 2
0x1401a9f40  jz      short loc_1401A9F4C
0x1401a9f42  mov     edi, 0C00000BBh
0x1401a9f47  jmp     loc_1401AA216
0x1401a9f4c  movzx   r9d, word ptr [r15+5Ch]
0x1401a9f51  lea     rax, [rbp+57h+var_A0]
0x1401a9f55  mov     edx, [r12+18h]
0x1401a9f5a  mov     r8d, 1
0x1401a9f60  mov     [rsp+110h+var_E8], rax
0x1401a9f65  mov     rcx, r14
0x1401a9f68  mov     byte ptr [rsp+110h+var_F0], 1
0x1401a9f6d  call    FlIfDeleteVirtualInterfaceHelper
0x1401a9f72  jmp     loc_1401AA200
0x1401a9f77  mov     ecx, [rax+4A0h]
0x1401a9f7d  lea     rdx, [rax+3B8h]
0x1401a9f84  mov     r9b, 1
0x1401a9f87  mov     [rsp+110h+var_F0], 0
0x1401a9f90  mov     r8b, r9b
0x1401a9f93  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x1401a9f9a  nop     dword ptr [rax+rax+00h]
0x1401a9f9f  test    al, al
0x1401a9fa1  jnz     short loc_1401A9FB2
0x1401a9fa3  mov     edi, 0C0000225h
0x1401a9fa8  mov     esi, 4
0x1401a9fad  jmp     loc_1401AA216
0x1401a9fb2  lea     r9, [rbp+57h+var_70]
0x1401a9fb6  lea     r8, [rbp+57h+var_60]
0x1401a9fba  lea     rdx, [rbp+57h+var_9C]
0x1401a9fbe  lea     rcx, [r12+8]
0x1401a9fc3  call    FlIfFindCompartment
0x1401a9fc8  mov     edi, eax
0x1401a9fca  test    eax, eax
0x1401a9fcc  jns     short loc_1401A9FD8
0x1401a9fce  mov     esi, 6
0x1401a9fd3  jmp     loc_1401AA216
0x1401a9fd8  mov     ecx, [rbp+57h+var_9C]
0x1401a9fdb  lea     rdx, [rbp+57h+var_70]
0x1401a9fdf  mov     r9b, 1
0x1401a9fe2  xor     edi, edi
0x1401a9fe4  mov     r8b, r9b
0x1401a9fe7  mov     [rsp+110h+var_F0], rdi
0x1401a9fec  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x1401a9ff3  nop     dword ptr [rax+rax+00h]
0x1401a9ff8  test    al, al
0x1401a9ffa  jnz     short loc_1401AA00B
0x1401a9ffc  mov     edi, 0C0000225h
0x1401aa001  mov     esi, 3
0x1401aa006  jmp     loc_1401AA216
0x1401aa00b  mov     rcx, r14
0x1401aa00e  call    FlpCreateClientInterface
0x1401aa013  mov     r15, rax
0x1401aa016  test    rax, rax
0x1401aa019  jnz     short loc_1401AA02C
0x1401aa01b  mov     edi, 0C000009Ah
0x1401aa020  lea     esi, [rax+1]
0x1401aa023  mov     r15, [rbp+57h+var_90]
0x1401aa027  jmp     loc_1401AA216
0x1401aa02c  call    cs:__imp_KeEnterCriticalRegion
0x1401aa033  nop     dword ptr [rax+rax+00h]
0x1401aa038  mov     dl, 1; Wait
0x1401aa03a  lea     rcx, Resource; Resource
0x1401aa041  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401aa048  nop     dword ptr [rax+rax+00h]
0x1401aa04d  mov     rcx, [r14+490h]
0x1401aa054  mov     edx, [r12+18h]
0x1401aa059  call    FlIfpFindVirtualInterfaceUnderLock
0x1401aa05e  test    rax, rax
0x1401aa061  jnz     short loc_1401AA090
0x1401aa063  lea     r8, [rbp+57h+var_88]
0x1401aa067  mov     [rbp+57h+var_88], rdi
0x1401aa06b  call    FlIfpQueryVirtualInterfaceLuid
0x1401aa070  test    eax, eax
0x1401aa072  js      short loc_1401AA090
0x1401aa074  mov     ecx, 2
0x1401aa079  lea     rdx, [rbp+57h+var_88]
0x1401aa07d  call    InternalCleanupPersistentStore
0x1401aa082  mov     ecx, 17h
0x1401aa087  lea     rdx, [rbp+57h+var_88]
0x1401aa08b  call    InternalCleanupPersistentStore
0x1401aa090  mov     r8d, [r12+18h]
0x1401aa095  lea     rax, [rbp+57h+var_A0]
0x1401aa099  mov     [rsp+110h+var_A8], rax
0x1401aa09e  lea     rdx, [r12+8]
0x1401aa0a3  lea     rax, [rbp+57h+var_98]
0x1401aa0a7  mov     r9d, r13d
0x1401aa0aa  mov     [rsp+110h+var_B0], rax
0x1401aa0af  mov     rcx, r14
0x1401aa0b2  lea     rax, [rbp+57h+var_80]
0x1401aa0b6  mov     [rsp+110h+var_B8], rax
0x1401aa0bb  mov     rax, [rbp+57h+var_90]
0x1401aa0bf  movzx   eax, word ptr [rax+5Ch]
0x1401aa0c3  mov     [rsp+110h+var_C0], ax
0x1401aa0c8  lea     rax, [rbp+57h+var_60]
0x1401aa0cc  mov     [rsp+110h+var_C8], rax
0x1401aa0d1  lea     rax, [rbp+57h+var_70]
0x1401aa0d5  mov     [rsp+110h+var_D0], rax
0x1401aa0da  mov     eax, [rbp+57h+var_9C]
0x1401aa0dd  mov     [rsp+110h+var_D8], eax
0x1401aa0e1  mov     [rsp+110h+var_E0], di
0x1401aa0e6  mov     [rsp+110h+var_E8], rdi
0x1401aa0eb  mov     dword ptr [rsp+110h+var_F0], 1
0x1401aa0f3  call    FlIfCreateVirtualInterface
0x1401aa0f8  mov     edi, eax
0x1401aa0fa  test    eax, eax
0x1401aa0fc  jns     short loc_1401AA12D
0x1401aa0fe  lea     rcx, Resource; Resource
0x1401aa105  call    cs:__imp_ExReleaseResourceLite
0x1401aa10c  nop     dword ptr [rax+rax+00h]
0x1401aa111  call    cs:__imp_KeLeaveCriticalRegion
0x1401aa118  nop     dword ptr [rax+rax+00h]
0x1401aa11d  mov     rcx, r15
0x1401aa120  call    FlpDereferenceClientInterface
0x1401aa125  mov     esi, [rbp+57h+var_A0]
0x1401aa128  jmp     loc_1401AA023
0x1401aa12d  mov     rax, [rbp+57h+var_80]
0x1401aa131  movups  xmm0, cs:FlIfIsolationTag
0x1401aa138  mov     rcx, [rbp+57h+var_78]
0x1401aa13c  mov     [r15+58h], rax
0x1401aa140  mov     eax, [rbp+57h+var_98]
0x1401aa143  mov     [r15+60h], eax
0x1401aa147  mov     eax, [rbp+57h+var_9C]
0x1401aa14a  mov     [r15+68h], eax
0x1401aa14e  mov     eax, [r12+18h]
0x1401aa153  mov     [r15+64h], eax
0x1401aa157  mov     [r15+80h], r13d
0x1401aa15e  movdqu  xmmword ptr [r15+6Ch], xmm0
0x1401aa164  test    rcx, rcx
0x1401aa167  jz      short loc_1401AA181
0x1401aa169  mov     cl, [rcx]
0x1401aa16b  cmp     cl, 0FFh
0x1401aa16e  jz      short loc_1401AA181
0x1401aa170  mov     al, [r15+40h]
0x1401aa174  add     cl, cl
0x1401aa176  xor     cl, al
0x1401aa178  and     cl, 2
0x1401aa17b  xor     cl, al
0x1401aa17d  mov     [r15+40h], cl
0x1401aa181  mov     rcx, r15; Entry
0x1401aa184  call    FlpAddInterface
0x1401aa189  lea     rcx, Resource; Resource
0x1401aa190  mov     edi, eax
0x1401aa192  call    cs:__imp_ExReleaseResourceLite
0x1401aa199  nop     dword ptr [rax+rax+00h]
0x1401aa19e  call    cs:__imp_KeLeaveCriticalRegion
0x1401aa1a5  nop     dword ptr [rax+rax+00h]
0x1401aa1aa  test    edi, edi
0x1401aa1ac  jns     loc_1401AA23F
0x1401aa1b2  mov     edx, [r12+18h]
0x1401aa1b7  lea     rax, [rbp+57h+var_98]
0x1401aa1bb  mov     [rsp+110h+var_F0], rax
0x1401aa1c0  mov     esi, 13h
0x1401aa1c5  mov     rax, [rbp+57h+var_90]
0x1401aa1c9  mov     rcx, r14
0x1401aa1cc  mov     [rbp+57h+var_98], 0
0x1401aa1d3  lea     r8d, [rsi-12h]
0x1401aa1d7  movzx   r9d, word ptr [rax+5Ch]
0x1401aa1dc  call    FlIfDeleteVirtualInterface
0x1401aa1e1  mov     rcx, r15
0x1401aa1e4  call    FlpDereferenceClientInterface
0x1401aa1e9  jmp     loc_1401AA023
0x1401aa1ee  lea     r9, [rbp+57h+var_A0]
0x1401aa1f2  mov     r8, rdi
0x1401aa1f5  mov     rdx, r12
0x1401aa1f8  mov     rcx, r14
0x1401aa1fb  call    FlpSetVirtualInterfaceHelper
0x1401aa200  mov     edi, eax
0x1401aa202  test    eax, eax
0x1401aa204  jns     short loc_1401AA23F
0x1401aa206  mov     esi, [rbp+57h+var_A0]
0x1401aa209  jmp     short loc_1401AA216
0x1401aa20b  mov     edi, 0C000000Dh
0x1401aa210  lea     rbx, [rdx+30h]
0x1401aa214  xor     esi, esi
0x1401aa216  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+6, 0
0x1401aa21d  jge     short loc_1401AA23A
0x1401aa21f  movzx   edx, word ptr [r15+5Ch]
0x1401aa224  mov     r9d, edi
0x1401aa227  mov     ecx, [rbx]
0x1401aa229  mov     r8, r12
0x1401aa22c  mov     byte ptr [rsp+110h+var_E8], 1
0x1401aa231  mov     dword ptr [rsp+110h+var_F0], esi
0x1401aa235  call    FlpLogVirtualIfCtlError
0x1401aa23a  test    r14, r14
0x1401aa23d  jz      short loc_1401AA247
0x1401aa23f  mov     rcx, r14
0x1401aa242  call    FlpDereferenceInterface
0x1401aa247  mov     eax, edi
0x1401aa249  mov     rcx, [rbp+57h+var_50]
0x1401aa24d  xor     rcx, rsp; StackCookie
0x1401aa250  call    __security_check_cookie
0x1401aa255  add     rsp, 0D8h
0x1401aa25c  pop     r15
0x1401aa25e  pop     r14
0x1401aa260  pop     r13
0x1401aa262  pop     r12
0x1401aa264  pop     rdi
0x1401aa265  pop     rsi
0x1401aa266  pop     rbx
0x1401aa267  pop     rbp
0x1401aa268  retn
```
