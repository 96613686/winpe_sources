# FlSetAllVirtualInterfaceParameters

- ea: `0x1401a8140`
- end: `0x1401a856a`
- name: `FlSetAllVirtualInterfaceParameters`
- size: `1066`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x1400c54b0`
- `0x1400c55d4`
- `0x1400c724c`
- `0x1400c7da4`
- `0x140148598`
- `0x1401a6318`
- `0x1401a6a60`
- `0x1401a6d8c`
- `0x1401a7024`
- `0x1401a7d88`
- `0x1401a7f30`
- `0x1401a8140`
- `0x1401a8640`
- `0x1401a87e8`
- `0x1401b3138`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a8411`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a849e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a8411`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a849e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a8405`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a8492`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a8405`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a8492`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a8341`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a8341`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a832c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a832c`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a8293`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a82ec`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a8293`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a82ec`

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
0x1401a8140  push    rbp
0x1401a8142  push    rbx
0x1401a8143  push    rsi
0x1401a8144  push    rdi
0x1401a8145  push    r12
0x1401a8147  push    r13
0x1401a8149  push    r14
0x1401a814b  push    r15
0x1401a814d  lea     rbp, [rsp-1Fh]
0x1401a8152  sub     rsp, 0D8h
0x1401a8159  mov     rax, cs:__security_cookie
0x1401a8160  xor     rax, rsp
0x1401a8163  mov     [rbp+57h+var_50], rax
0x1401a8167  mov     rax, [rcx]
0x1401a816a  xor     r14d, r14d
0x1401a816d  xorps   xmm0, xmm0
0x1401a8170  mov     r12, [rcx+10h]
0x1401a8174  xorps   xmm1, xmm1
0x1401a8177  mov     rdx, rcx
0x1401a817a  mov     [rbp+57h+var_80], r14
0x1401a817e  lea     esi, [r14+16h]
0x1401a8182  mov     r15, [rax+28h]
0x1401a8186  mov     [rbp+57h+var_90], r15
0x1401a818a  mov     [rbp+57h+var_A0], esi
0x1401a818d  mov     [rbp+57h+var_9C], r14d
0x1401a8191  movups  [rbp+57h+var_60], xmm0
0x1401a8195  mov     [rbp+57h+var_98], r14d
0x1401a8199  movups  [rbp+57h+var_70], xmm1
0x1401a819d  cmp     [rcx+34h], r14d
0x1401a81a1  jnz     loc_1401A850B
0x1401a81a7  lea     rbx, [rcx+30h]
0x1401a81ab  mov     eax, [rbx]
0x1401a81ad  cmp     eax, 4
0x1401a81b0  jz      loc_1401A850B
0x1401a81b6  cmp     [r12+18h], r14d
0x1401a81bb  jnz     short loc_1401A81C5
0x1401a81bd  test    eax, eax
0x1401a81bf  jnz     loc_1401A850B
0x1401a81c5  mov     rdi, [rcx+20h]
0x1401a81c9  mov     [rbp+57h+var_78], rdi
0x1401a81cd  test    eax, eax
0x1401a81cf  jnz     short loc_1401A81DA
0x1401a81d1  test    rdi, rdi
0x1401a81d4  jz      loc_1401A850B
0x1401a81da  mov     ecx, [r12+1Ch]
0x1401a81df  cmp     ecx, 2
0x1401a81e2  ja      loc_1401A850B
0x1401a81e8  test    ecx, ecx
0x1401a81ea  jz      short loc_1401A8203
0x1401a81ec  sub     ecx, 1
0x1401a81ef  jz      short loc_1401A81FB
0x1401a81f1  cmp     ecx, 1
0x1401a81f4  jnz     short loc_1401A8203
0x1401a81f6  mov     r13d, ecx
0x1401a81f9  jmp     short loc_1401A8206
0x1401a81fb  mov     r13d, 3
0x1401a8201  jmp     short loc_1401A8206
0x1401a8203  mov     r13d, r14d
0x1401a8206  mov     rdx, [r12]
0x1401a820a  lea     rcx, [r15+1B8h]
0x1401a8211  xor     r8d, r8d
0x1401a8214  call    FlpFindInterface
0x1401a8219  mov     r14, rax
0x1401a821c  test    rax, rax
0x1401a821f  jnz     short loc_1401A822E
0x1401a8221  mov     edi, 0C0000225h
0x1401a8226  lea     esi, [rax+8]
0x1401a8229  jmp     loc_1401A8516
0x1401a822e  mov     ecx, [rbx]
0x1401a8230  test    ecx, ecx
0x1401a8232  jz      loc_1401A84EE
0x1401a8238  sub     ecx, 1
0x1401a823b  jz      short loc_1401A8277
0x1401a823d  cmp     ecx, 2
0x1401a8240  jz      short loc_1401A824C
0x1401a8242  mov     edi, 0C00000BBh
0x1401a8247  jmp     loc_1401A8516
0x1401a824c  movzx   r9d, word ptr [r15+5Ch]
0x1401a8251  lea     rax, [rbp+57h+var_A0]
0x1401a8255  mov     edx, [r12+18h]
0x1401a825a  mov     r8d, 1
0x1401a8260  mov     [rsp+110h+var_E8], rax
0x1401a8265  mov     rcx, r14
0x1401a8268  mov     byte ptr [rsp+110h+var_F0], 1
0x1401a826d  call    FlIfDeleteVirtualInterfaceHelper
0x1401a8272  jmp     loc_1401A8500
0x1401a8277  mov     ecx, [rax+4A0h]
0x1401a827d  lea     rdx, [rax+3B8h]
0x1401a8284  mov     r9b, 1
0x1401a8287  mov     [rsp+110h+var_F0], 0
0x1401a8290  mov     r8b, r9b
0x1401a8293  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x1401a829a  nop     dword ptr [rax+rax+00h]
0x1401a829f  test    al, al
0x1401a82a1  jnz     short loc_1401A82B2
0x1401a82a3  mov     edi, 0C0000225h
0x1401a82a8  mov     esi, 4
0x1401a82ad  jmp     loc_1401A8516
0x1401a82b2  lea     r9, [rbp+57h+var_70]
0x1401a82b6  lea     r8, [rbp+57h+var_60]
0x1401a82ba  lea     rdx, [rbp+57h+var_9C]
0x1401a82be  lea     rcx, [r12+8]
0x1401a82c3  call    FlIfFindCompartment
0x1401a82c8  mov     edi, eax
0x1401a82ca  test    eax, eax
0x1401a82cc  jns     short loc_1401A82D8
0x1401a82ce  mov     esi, 6
0x1401a82d3  jmp     loc_1401A8516
0x1401a82d8  mov     ecx, [rbp+57h+var_9C]
0x1401a82db  lea     rdx, [rbp+57h+var_70]
0x1401a82df  mov     r9b, 1
0x1401a82e2  xor     edi, edi
0x1401a82e4  mov     r8b, r9b
0x1401a82e7  mov     [rsp+110h+var_F0], rdi
0x1401a82ec  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x1401a82f3  nop     dword ptr [rax+rax+00h]
0x1401a82f8  test    al, al
0x1401a82fa  jnz     short loc_1401A830B
0x1401a82fc  mov     edi, 0C0000225h
0x1401a8301  mov     esi, 3
0x1401a8306  jmp     loc_1401A8516
0x1401a830b  mov     rcx, r14
0x1401a830e  call    FlpCreateClientInterface
0x1401a8313  mov     r15, rax
0x1401a8316  test    rax, rax
0x1401a8319  jnz     short loc_1401A832C
0x1401a831b  mov     edi, 0C000009Ah
0x1401a8320  lea     esi, [rax+1]
0x1401a8323  mov     r15, [rbp+57h+var_90]
0x1401a8327  jmp     loc_1401A8516
0x1401a832c  call    cs:__imp_KeEnterCriticalRegion
0x1401a8333  nop     dword ptr [rax+rax+00h]
0x1401a8338  mov     dl, 1; Wait
0x1401a833a  lea     rcx, Resource; Resource
0x1401a8341  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401a8348  nop     dword ptr [rax+rax+00h]
0x1401a834d  mov     rcx, [r14+490h]
0x1401a8354  mov     edx, [r12+18h]
0x1401a8359  call    FlIfpFindVirtualInterfaceUnderLock
0x1401a835e  test    rax, rax
0x1401a8361  jnz     short loc_1401A8390
0x1401a8363  lea     r8, [rbp+57h+var_88]
0x1401a8367  mov     [rbp+57h+var_88], rdi
0x1401a836b  call    FlIfpQueryVirtualInterfaceLuid
0x1401a8370  test    eax, eax
0x1401a8372  js      short loc_1401A8390
0x1401a8374  mov     ecx, 2
0x1401a8379  lea     rdx, [rbp+57h+var_88]
0x1401a837d  call    InternalCleanupPersistentStore
0x1401a8382  mov     ecx, 17h
0x1401a8387  lea     rdx, [rbp+57h+var_88]
0x1401a838b  call    InternalCleanupPersistentStore
0x1401a8390  mov     r8d, [r12+18h]
0x1401a8395  lea     rax, [rbp+57h+var_A0]
0x1401a8399  mov     [rsp+110h+var_A8], rax
0x1401a839e  lea     rdx, [r12+8]
0x1401a83a3  lea     rax, [rbp+57h+var_98]
0x1401a83a7  mov     r9d, r13d
0x1401a83aa  mov     [rsp+110h+var_B0], rax
0x1401a83af  mov     rcx, r14
0x1401a83b2  lea     rax, [rbp+57h+var_80]
0x1401a83b6  mov     [rsp+110h+var_B8], rax
0x1401a83bb  mov     rax, [rbp+57h+var_90]
0x1401a83bf  movzx   eax, word ptr [rax+5Ch]
0x1401a83c3  mov     [rsp+110h+var_C0], ax
0x1401a83c8  lea     rax, [rbp+57h+var_60]
0x1401a83cc  mov     [rsp+110h+var_C8], rax
0x1401a83d1  lea     rax, [rbp+57h+var_70]
0x1401a83d5  mov     [rsp+110h+var_D0], rax
0x1401a83da  mov     eax, [rbp+57h+var_9C]
0x1401a83dd  mov     [rsp+110h+var_D8], eax
0x1401a83e1  mov     [rsp+110h+var_E0], di
0x1401a83e6  mov     [rsp+110h+var_E8], rdi
0x1401a83eb  mov     dword ptr [rsp+110h+var_F0], 1
0x1401a83f3  call    FlIfCreateVirtualInterface
0x1401a83f8  mov     edi, eax
0x1401a83fa  test    eax, eax
0x1401a83fc  jns     short loc_1401A842D
0x1401a83fe  lea     rcx, Resource; Resource
0x1401a8405  call    cs:__imp_ExReleaseResourceLite
0x1401a840c  nop     dword ptr [rax+rax+00h]
0x1401a8411  call    cs:__imp_KeLeaveCriticalRegion
0x1401a8418  nop     dword ptr [rax+rax+00h]
0x1401a841d  mov     rcx, r15
0x1401a8420  call    FlpDereferenceClientInterface
0x1401a8425  mov     esi, [rbp+57h+var_A0]
0x1401a8428  jmp     loc_1401A8323
0x1401a842d  mov     rax, [rbp+57h+var_80]
0x1401a8431  movups  xmm0, cs:FlIfIsolationTag
0x1401a8438  mov     rcx, [rbp+57h+var_78]
0x1401a843c  mov     [r15+58h], rax
0x1401a8440  mov     eax, [rbp+57h+var_98]
0x1401a8443  mov     [r15+60h], eax
0x1401a8447  mov     eax, [rbp+57h+var_9C]
0x1401a844a  mov     [r15+68h], eax
0x1401a844e  mov     eax, [r12+18h]
0x1401a8453  mov     [r15+64h], eax
0x1401a8457  mov     [r15+80h], r13d
0x1401a845e  movdqu  xmmword ptr [r15+6Ch], xmm0
0x1401a8464  test    rcx, rcx
0x1401a8467  jz      short loc_1401A8481
0x1401a8469  mov     cl, [rcx]
0x1401a846b  cmp     cl, 0FFh
0x1401a846e  jz      short loc_1401A8481
0x1401a8470  mov     al, [r15+40h]
0x1401a8474  add     cl, cl
0x1401a8476  xor     cl, al
0x1401a8478  and     cl, 2
0x1401a847b  xor     cl, al
0x1401a847d  mov     [r15+40h], cl
0x1401a8481  mov     rcx, r15; Entry
0x1401a8484  call    FlpAddInterface
0x1401a8489  lea     rcx, Resource; Resource
0x1401a8490  mov     edi, eax
0x1401a8492  call    cs:__imp_ExReleaseResourceLite
0x1401a8499  nop     dword ptr [rax+rax+00h]
0x1401a849e  call    cs:__imp_KeLeaveCriticalRegion
0x1401a84a5  nop     dword ptr [rax+rax+00h]
0x1401a84aa  test    edi, edi
0x1401a84ac  jns     loc_1401A853F
0x1401a84b2  mov     edx, [r12+18h]
0x1401a84b7  lea     rax, [rbp+57h+var_98]
0x1401a84bb  mov     [rsp+110h+var_F0], rax
0x1401a84c0  mov     esi, 13h
0x1401a84c5  mov     rax, [rbp+57h+var_90]
0x1401a84c9  mov     rcx, r14
0x1401a84cc  mov     [rbp+57h+var_98], 0
0x1401a84d3  lea     r8d, [rsi-12h]
0x1401a84d7  movzx   r9d, word ptr [rax+5Ch]
0x1401a84dc  call    FlIfDeleteVirtualInterface
0x1401a84e1  mov     rcx, r15
0x1401a84e4  call    FlpDereferenceClientInterface
0x1401a84e9  jmp     loc_1401A8323
0x1401a84ee  lea     r9, [rbp+57h+var_A0]
0x1401a84f2  mov     r8, rdi
0x1401a84f5  mov     rdx, r12
0x1401a84f8  mov     rcx, r14
0x1401a84fb  call    FlpSetVirtualInterfaceHelper
0x1401a8500  mov     edi, eax
0x1401a8502  test    eax, eax
0x1401a8504  jns     short loc_1401A853F
0x1401a8506  mov     esi, [rbp+57h+var_A0]
0x1401a8509  jmp     short loc_1401A8516
0x1401a850b  mov     edi, 0C000000Dh
0x1401a8510  lea     rbx, [rdx+30h]
0x1401a8514  xor     esi, esi
0x1401a8516  cmp     byte ptr cs:WPP_MAIN_CB+14Eh, 0
0x1401a851d  jge     short loc_1401A853A
0x1401a851f  movzx   edx, word ptr [r15+5Ch]
0x1401a8524  mov     r9d, edi
0x1401a8527  mov     ecx, [rbx]
0x1401a8529  mov     r8, r12
0x1401a852c  mov     byte ptr [rsp+110h+var_E8], 1
0x1401a8531  mov     dword ptr [rsp+110h+var_F0], esi
0x1401a8535  call    FlpLogVirtualIfCtlError
0x1401a853a  test    r14, r14
0x1401a853d  jz      short loc_1401A8547
0x1401a853f  mov     rcx, r14
0x1401a8542  call    FlpDereferenceInterface
0x1401a8547  mov     eax, edi
0x1401a8549  mov     rcx, [rbp+57h+var_50]
0x1401a854d  xor     rcx, rsp; StackCookie
0x1401a8550  call    __security_check_cookie
0x1401a8555  add     rsp, 0D8h
0x1401a855c  pop     r15
0x1401a855e  pop     r14
0x1401a8560  pop     r13
0x1401a8562  pop     r12
0x1401a8564  pop     rdi
0x1401a8565  pop     rsi
0x1401a8566  pop     rbx
0x1401a8567  pop     rbp
0x1401a8568  retn
```
