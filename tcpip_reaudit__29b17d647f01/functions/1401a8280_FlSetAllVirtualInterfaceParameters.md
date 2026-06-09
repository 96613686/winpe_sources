# FlSetAllVirtualInterfaceParameters

- ea: `0x1401a8280`
- end: `0x1401a86aa`
- name: `FlSetAllVirtualInterfaceParameters`
- size: `1066`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x1400c5290`
- `0x1400c53b4`
- `0x1400c702c`
- `0x1400c7b84`
- `0x140148728`
- `0x1401a6458`
- `0x1401a6ba0`
- `0x1401a6ecc`
- `0x1401a7164`
- `0x1401a7ec8`
- `0x1401a8070`
- `0x1401a8280`
- `0x1401a8780`
- `0x1401a8928`
- `0x1401b3278`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a8551`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a85de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a8551`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a85de`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a8545`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a85d2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a8545`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a85d2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a8481`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a8481`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a846c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a846c`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a83d3`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a842c`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a83d3`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a842c`

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
  if ( *((char *)&WPP_MAIN_CB.Reserved + 14) < 0 )
    FlpLogVirtualIfCtlError(*v7, *(unsigned __int16 *)(v6 + 92), v3, Compartment, v5, 1);
  if ( v2 )
    goto LABEL_47;
  return (unsigned int)Compartment;
}

```

## disassembly

```asm
0x1401a8280  push    rbp
0x1401a8282  push    rbx
0x1401a8283  push    rsi
0x1401a8284  push    rdi
0x1401a8285  push    r12
0x1401a8287  push    r13
0x1401a8289  push    r14
0x1401a828b  push    r15
0x1401a828d  lea     rbp, [rsp-1Fh]
0x1401a8292  sub     rsp, 0D8h
0x1401a8299  mov     rax, cs:__security_cookie
0x1401a82a0  xor     rax, rsp
0x1401a82a3  mov     [rbp+57h+var_50], rax
0x1401a82a7  mov     rax, [rcx]
0x1401a82aa  xor     r14d, r14d
0x1401a82ad  xorps   xmm0, xmm0
0x1401a82b0  mov     r12, [rcx+10h]
0x1401a82b4  xorps   xmm1, xmm1
0x1401a82b7  mov     rdx, rcx
0x1401a82ba  mov     [rbp+57h+var_80], r14
0x1401a82be  lea     esi, [r14+16h]
0x1401a82c2  mov     r15, [rax+28h]
0x1401a82c6  mov     [rbp+57h+var_90], r15
0x1401a82ca  mov     [rbp+57h+var_A0], esi
0x1401a82cd  mov     [rbp+57h+var_9C], r14d
0x1401a82d1  movups  [rbp+57h+var_60], xmm0
0x1401a82d5  mov     [rbp+57h+var_98], r14d
0x1401a82d9  movups  [rbp+57h+var_70], xmm1
0x1401a82dd  cmp     [rcx+34h], r14d
0x1401a82e1  jnz     loc_1401A864B
0x1401a82e7  lea     rbx, [rcx+30h]
0x1401a82eb  mov     eax, [rbx]
0x1401a82ed  cmp     eax, 4
0x1401a82f0  jz      loc_1401A864B
0x1401a82f6  cmp     [r12+18h], r14d
0x1401a82fb  jnz     short loc_1401A8305
0x1401a82fd  test    eax, eax
0x1401a82ff  jnz     loc_1401A864B
0x1401a8305  mov     rdi, [rcx+20h]
0x1401a8309  mov     [rbp+57h+var_78], rdi
0x1401a830d  test    eax, eax
0x1401a830f  jnz     short loc_1401A831A
0x1401a8311  test    rdi, rdi
0x1401a8314  jz      loc_1401A864B
0x1401a831a  mov     ecx, [r12+1Ch]
0x1401a831f  cmp     ecx, 2
0x1401a8322  ja      loc_1401A864B
0x1401a8328  test    ecx, ecx
0x1401a832a  jz      short loc_1401A8343
0x1401a832c  sub     ecx, 1
0x1401a832f  jz      short loc_1401A833B
0x1401a8331  cmp     ecx, 1
0x1401a8334  jnz     short loc_1401A8343
0x1401a8336  mov     r13d, ecx
0x1401a8339  jmp     short loc_1401A8346
0x1401a833b  mov     r13d, 3
0x1401a8341  jmp     short loc_1401A8346
0x1401a8343  mov     r13d, r14d
0x1401a8346  mov     rdx, [r12]
0x1401a834a  lea     rcx, [r15+1B8h]
0x1401a8351  xor     r8d, r8d
0x1401a8354  call    FlpFindInterface
0x1401a8359  mov     r14, rax
0x1401a835c  test    rax, rax
0x1401a835f  jnz     short loc_1401A836E
0x1401a8361  mov     edi, 0C0000225h
0x1401a8366  lea     esi, [rax+8]
0x1401a8369  jmp     loc_1401A8656
0x1401a836e  mov     ecx, [rbx]
0x1401a8370  test    ecx, ecx
0x1401a8372  jz      loc_1401A862E
0x1401a8378  sub     ecx, 1
0x1401a837b  jz      short loc_1401A83B7
0x1401a837d  cmp     ecx, 2
0x1401a8380  jz      short loc_1401A838C
0x1401a8382  mov     edi, 0C00000BBh
0x1401a8387  jmp     loc_1401A8656
0x1401a838c  movzx   r9d, word ptr [r15+5Ch]
0x1401a8391  lea     rax, [rbp+57h+var_A0]
0x1401a8395  mov     edx, [r12+18h]
0x1401a839a  mov     r8d, 1
0x1401a83a0  mov     [rsp+110h+var_E8], rax
0x1401a83a5  mov     rcx, r14
0x1401a83a8  mov     byte ptr [rsp+110h+var_F0], 1
0x1401a83ad  call    FlIfDeleteVirtualInterfaceHelper
0x1401a83b2  jmp     loc_1401A8640
0x1401a83b7  mov     ecx, [rax+4A0h]
0x1401a83bd  lea     rdx, [rax+3B8h]
0x1401a83c4  mov     r9b, 1
0x1401a83c7  mov     [rsp+110h+var_F0], 0
0x1401a83d0  mov     r8b, r9b
0x1401a83d3  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x1401a83da  nop     dword ptr [rax+rax+00h]
0x1401a83df  test    al, al
0x1401a83e1  jnz     short loc_1401A83F2
0x1401a83e3  mov     edi, 0C0000225h
0x1401a83e8  mov     esi, 4
0x1401a83ed  jmp     loc_1401A8656
0x1401a83f2  lea     r9, [rbp+57h+var_70]
0x1401a83f6  lea     r8, [rbp+57h+var_60]
0x1401a83fa  lea     rdx, [rbp+57h+var_9C]
0x1401a83fe  lea     rcx, [r12+8]
0x1401a8403  call    FlIfFindCompartment
0x1401a8408  mov     edi, eax
0x1401a840a  test    eax, eax
0x1401a840c  jns     short loc_1401A8418
0x1401a840e  mov     esi, 6
0x1401a8413  jmp     loc_1401A8656
0x1401a8418  mov     ecx, [rbp+57h+var_9C]
0x1401a841b  lea     rdx, [rbp+57h+var_70]
0x1401a841f  mov     r9b, 1
0x1401a8422  xor     edi, edi
0x1401a8424  mov     r8b, r9b
0x1401a8427  mov     [rsp+110h+var_F0], rdi
0x1401a842c  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x1401a8433  nop     dword ptr [rax+rax+00h]
0x1401a8438  test    al, al
0x1401a843a  jnz     short loc_1401A844B
0x1401a843c  mov     edi, 0C0000225h
0x1401a8441  mov     esi, 3
0x1401a8446  jmp     loc_1401A8656
0x1401a844b  mov     rcx, r14
0x1401a844e  call    FlpCreateClientInterface
0x1401a8453  mov     r15, rax
0x1401a8456  test    rax, rax
0x1401a8459  jnz     short loc_1401A846C
0x1401a845b  mov     edi, 0C000009Ah
0x1401a8460  lea     esi, [rax+1]
0x1401a8463  mov     r15, [rbp+57h+var_90]
0x1401a8467  jmp     loc_1401A8656
0x1401a846c  call    cs:__imp_KeEnterCriticalRegion
0x1401a8473  nop     dword ptr [rax+rax+00h]
0x1401a8478  mov     dl, 1; Wait
0x1401a847a  lea     rcx, Resource; Resource
0x1401a8481  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401a8488  nop     dword ptr [rax+rax+00h]
0x1401a848d  mov     rcx, [r14+490h]
0x1401a8494  mov     edx, [r12+18h]
0x1401a8499  call    FlIfpFindVirtualInterfaceUnderLock
0x1401a849e  test    rax, rax
0x1401a84a1  jnz     short loc_1401A84D0
0x1401a84a3  lea     r8, [rbp+57h+var_88]
0x1401a84a7  mov     [rbp+57h+var_88], rdi
0x1401a84ab  call    FlIfpQueryVirtualInterfaceLuid
0x1401a84b0  test    eax, eax
0x1401a84b2  js      short loc_1401A84D0
0x1401a84b4  mov     ecx, 2
0x1401a84b9  lea     rdx, [rbp+57h+var_88]
0x1401a84bd  call    InternalCleanupPersistentStore
0x1401a84c2  mov     ecx, 17h
0x1401a84c7  lea     rdx, [rbp+57h+var_88]
0x1401a84cb  call    InternalCleanupPersistentStore
0x1401a84d0  mov     r8d, [r12+18h]
0x1401a84d5  lea     rax, [rbp+57h+var_A0]
0x1401a84d9  mov     [rsp+110h+var_A8], rax
0x1401a84de  lea     rdx, [r12+8]
0x1401a84e3  lea     rax, [rbp+57h+var_98]
0x1401a84e7  mov     r9d, r13d
0x1401a84ea  mov     [rsp+110h+var_B0], rax
0x1401a84ef  mov     rcx, r14
0x1401a84f2  lea     rax, [rbp+57h+var_80]
0x1401a84f6  mov     [rsp+110h+var_B8], rax
0x1401a84fb  mov     rax, [rbp+57h+var_90]
0x1401a84ff  movzx   eax, word ptr [rax+5Ch]
0x1401a8503  mov     [rsp+110h+var_C0], ax
0x1401a8508  lea     rax, [rbp+57h+var_60]
0x1401a850c  mov     [rsp+110h+var_C8], rax
0x1401a8511  lea     rax, [rbp+57h+var_70]
0x1401a8515  mov     [rsp+110h+var_D0], rax
0x1401a851a  mov     eax, [rbp+57h+var_9C]
0x1401a851d  mov     [rsp+110h+var_D8], eax
0x1401a8521  mov     [rsp+110h+var_E0], di
0x1401a8526  mov     [rsp+110h+var_E8], rdi
0x1401a852b  mov     dword ptr [rsp+110h+var_F0], 1
0x1401a8533  call    FlIfCreateVirtualInterface
0x1401a8538  mov     edi, eax
0x1401a853a  test    eax, eax
0x1401a853c  jns     short loc_1401A856D
0x1401a853e  lea     rcx, Resource; Resource
0x1401a8545  call    cs:__imp_ExReleaseResourceLite
0x1401a854c  nop     dword ptr [rax+rax+00h]
0x1401a8551  call    cs:__imp_KeLeaveCriticalRegion
0x1401a8558  nop     dword ptr [rax+rax+00h]
0x1401a855d  mov     rcx, r15
0x1401a8560  call    FlpDereferenceClientInterface
0x1401a8565  mov     esi, [rbp+57h+var_A0]
0x1401a8568  jmp     loc_1401A8463
0x1401a856d  mov     rax, [rbp+57h+var_80]
0x1401a8571  movups  xmm0, cs:FlIfIsolationTag
0x1401a8578  mov     rcx, [rbp+57h+var_78]
0x1401a857c  mov     [r15+58h], rax
0x1401a8580  mov     eax, [rbp+57h+var_98]
0x1401a8583  mov     [r15+60h], eax
0x1401a8587  mov     eax, [rbp+57h+var_9C]
0x1401a858a  mov     [r15+68h], eax
0x1401a858e  mov     eax, [r12+18h]
0x1401a8593  mov     [r15+64h], eax
0x1401a8597  mov     [r15+80h], r13d
0x1401a859e  movdqu  xmmword ptr [r15+6Ch], xmm0
0x1401a85a4  test    rcx, rcx
0x1401a85a7  jz      short loc_1401A85C1
0x1401a85a9  mov     cl, [rcx]
0x1401a85ab  cmp     cl, 0FFh
0x1401a85ae  jz      short loc_1401A85C1
0x1401a85b0  mov     al, [r15+40h]
0x1401a85b4  add     cl, cl
0x1401a85b6  xor     cl, al
0x1401a85b8  and     cl, 2
0x1401a85bb  xor     cl, al
0x1401a85bd  mov     [r15+40h], cl
0x1401a85c1  mov     rcx, r15; Entry
0x1401a85c4  call    FlpAddInterface
0x1401a85c9  lea     rcx, Resource; Resource
0x1401a85d0  mov     edi, eax
0x1401a85d2  call    cs:__imp_ExReleaseResourceLite
0x1401a85d9  nop     dword ptr [rax+rax+00h]
0x1401a85de  call    cs:__imp_KeLeaveCriticalRegion
0x1401a85e5  nop     dword ptr [rax+rax+00h]
0x1401a85ea  test    edi, edi
0x1401a85ec  jns     loc_1401A867F
0x1401a85f2  mov     edx, [r12+18h]
0x1401a85f7  lea     rax, [rbp+57h+var_98]
0x1401a85fb  mov     [rsp+110h+var_F0], rax
0x1401a8600  mov     esi, 13h
0x1401a8605  mov     rax, [rbp+57h+var_90]
0x1401a8609  mov     rcx, r14
0x1401a860c  mov     [rbp+57h+var_98], 0
0x1401a8613  lea     r8d, [rsi-12h]
0x1401a8617  movzx   r9d, word ptr [rax+5Ch]
0x1401a861c  call    FlIfDeleteVirtualInterface
0x1401a8621  mov     rcx, r15
0x1401a8624  call    FlpDereferenceClientInterface
0x1401a8629  jmp     loc_1401A8463
0x1401a862e  lea     r9, [rbp+57h+var_A0]
0x1401a8632  mov     r8, rdi
0x1401a8635  mov     rdx, r12
0x1401a8638  mov     rcx, r14
0x1401a863b  call    FlpSetVirtualInterfaceHelper
0x1401a8640  mov     edi, eax
0x1401a8642  test    eax, eax
0x1401a8644  jns     short loc_1401A867F
0x1401a8646  mov     esi, [rbp+57h+var_A0]
0x1401a8649  jmp     short loc_1401A8656
0x1401a864b  mov     edi, 0C000000Dh
0x1401a8650  lea     rbx, [rdx+30h]
0x1401a8654  xor     esi, esi
0x1401a8656  cmp     byte ptr cs:WPP_MAIN_CB+14Eh, 0
0x1401a865d  jge     short loc_1401A867A
0x1401a865f  movzx   edx, word ptr [r15+5Ch]
0x1401a8664  mov     r9d, edi
0x1401a8667  mov     ecx, [rbx]
0x1401a8669  mov     r8, r12
0x1401a866c  mov     byte ptr [rsp+110h+var_E8], 1
0x1401a8671  mov     dword ptr [rsp+110h+var_F0], esi
0x1401a8675  call    FlpLogVirtualIfCtlError
0x1401a867a  test    r14, r14
0x1401a867d  jz      short loc_1401A8687
0x1401a867f  mov     rcx, r14
0x1401a8682  call    FlpDereferenceInterface
0x1401a8687  mov     eax, edi
0x1401a8689  mov     rcx, [rbp+57h+var_50]
0x1401a868d  xor     rcx, rsp; StackCookie
0x1401a8690  call    __security_check_cookie
0x1401a8695  add     rsp, 0D8h
0x1401a869c  pop     r15
0x1401a869e  pop     r14
0x1401a86a0  pop     r13
0x1401a86a2  pop     r12
0x1401a86a4  pop     rdi
0x1401a86a5  pop     rsi
0x1401a86a6  pop     rbx
0x1401a86a7  pop     rbp
0x1401a86a8  retn
```
