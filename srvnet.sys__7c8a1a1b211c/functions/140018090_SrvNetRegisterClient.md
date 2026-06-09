# SrvNetRegisterClient

- ea: `0x140018090`
- end: `0x1400183ce`
- name: `SrvNetRegisterClient`
- size: `830`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callees

- `0x1400039ac`
- `0x140007360`
- `0x140007c60`
- `0x140015790`
- `0x140018090`
- `0x140018480`
- `0x14002a540`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400181f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400182ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001833f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400181f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400182ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001833f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001811b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001811b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001820f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400182ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018369`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001820f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400182ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018369`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400181ac`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400181ac`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018196`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018196`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001821e`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400182d9`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001821e`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400182d9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400181c3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400181c3`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001812e`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001812e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001823e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400182f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001823e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400182f9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018203`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400182be`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001835d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018203`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400182be`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001835d`

## pseudocode

```c
__int64 __fastcall SrvNetRegisterClient(unsigned __int16 *a1, __int64 *a2)
{
  __int64 PoolWithTag; // rax
  __int64 v5; // rbx
  KIRQL v7; // al
  PERESOURCE v8; // rdx
  unsigned __int16 v9; // cx
  __int64 v10; // r8

  *a2 = 0;
  PoolWithTag = SrvNetAllocatePoolWithTag(64, *a1 + 240LL, 1717719884);
  v5 = PoolWithTag;
  if ( PoolWithTag )
  {
    *(_DWORD *)(PoolWithTag + 128) = 1;
    KeInitializeSpinLock((PKSPIN_LOCK)(PoolWithTag + 120));
    ExInitializeResourceLite((PERESOURCE)(v5 + 16));
    *(_OWORD *)(v5 + 136) = *(_OWORD *)a1;
    *(_OWORD *)(v5 + 152) = *((_OWORD *)a1 + 1);
    *(_OWORD *)(v5 + 168) = *((_OWORD *)a1 + 2);
    *(_OWORD *)(v5 + 184) = *((_OWORD *)a1 + 3);
    *(_OWORD *)(v5 + 200) = *((_OWORD *)a1 + 4);
    *(_OWORD *)(v5 + 216) = *((_OWORD *)a1 + 5);
    *(_QWORD *)(v5 + 144) = v5 + 240;
    memmove((void *)(v5 + 240), *((const void **)a1 + 1), *a1);
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(SrvNetDeviceExtension, 1u);
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&SrvNetDeviceExtension[1]);
    v8 = SrvNetDeviceExtension;
    if ( SLODWORD(SrvNetDeviceExtension[5].SystemResourcesList.Flink) < 7 )
    {
      v9 = 0;
      while ( *(&SrvNetDeviceExtension[4].OwnerEntry.OwnerThread + v9) )
      {
        if ( ++v9 >= 7u )
        {
          if ( v9 == 7 )
          {
            KeReleaseSpinLock((PKSPIN_LOCK)&SrvNetDeviceExtension[1], v7);
            ExReleaseResourceLite(SrvNetDeviceExtension);
            KeLeaveCriticalRegion();
            ExDeleteResourceLite((PERESOURCE)(v5 + 16));
            SrvNetUpdateMemStatistics(*(unsigned int *)(v5 - 12), *(unsigned int *)(v5 - 16), 0);
            ExFreePoolWithTag((PVOID)(v5 - 16), 0);
            return 3221225665LL;
          }
          break;
        }
      }
      *(_DWORD *)(v5 + 232) = v9;
      *(_DWORD *)(v5 + 132) = 0;
      *(_BYTE *)(v5 + 237) = 0;
      ++LODWORD(v8[5].SystemResourcesList.Flink);
      *(&v8[4].OwnerEntry.OwnerThread + v9) = v5;
      *a2 = v5;
      KeReleaseSpinLock((PKSPIN_LOCK)&v8[1], v7);
      _InterlockedAdd((volatile signed __int32 *)&SrvNetDeviceExtension[1].SystemResourcesList.Blink, 1u);
      ExReleaseResourceLite(SrvNetDeviceExtension);
      KeLeaveCriticalRegion();
      LOBYTE(v10) = 1;
      SrvNetTriggerScavenger(0, 0, v10);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Zq(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          (unsigned int)WPP_b2c5afd6f6c2384decec4e1014c730bc_Traceguids,
          (_DWORD)a1,
          v5);
      }
      return 0;
    }
    else
    {
      KeReleaseSpinLock((PKSPIN_LOCK)&SrvNetDeviceExtension[1], v7);
      ExReleaseResourceLite(SrvNetDeviceExtension);
      KeLeaveCriticalRegion();
      ExDeleteResourceLite((PERESOURCE)(v5 + 16));
      SrvNetUpdateMemStatistics(*(unsigned int *)(v5 - 12), *(unsigned int *)(v5 - 16), 0);
      ExFreePoolWithTag((PVOID)(v5 - 16), 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_b2c5afd6f6c2384decec4e1014c730bc_Traceguids);
      }
      return 3221225665LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b2c5afd6f6c2384decec4e1014c730bc_Traceguids);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140018090  push    rbx
0x140018092  push    rbp
0x140018093  push    rsi
0x140018094  push    rdi
0x140018095  push    r14
0x140018097  sub     rsp, 30h
0x14001809b  mov     r14, rdx
0x14001809e  mov     qword ptr [rdx], 0
0x1400180a5  movzx   edx, word ptr [rcx]
0x1400180a8  mov     rsi, rcx
0x1400180ab  add     rdx, 0F0h
0x1400180b2  mov     ecx, 40h ; '@'
0x1400180b7  mov     r8d, 6662534Ch
0x1400180bd  call    SrvNetAllocatePoolWithTag
0x1400180c2  mov     rbx, rax
0x1400180c5  test    rax, rax
0x1400180c8  jnz     short loc_14001810C
0x1400180ca  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400180d1  lea     rax, WPP_GLOBAL_Control
0x1400180d8  cmp     rcx, rax
0x1400180db  jz      short loc_140018102
0x1400180dd  test    dword ptr [rcx+2Ch], 1000h
0x1400180e4  jz      short loc_140018102
0x1400180e6  lea     edi, [rbx+1]
0x1400180e9  cmp     [rcx+29h], dil
0x1400180ed  jb      short loc_140018102
0x1400180ef  mov     rcx, [rcx+18h]
0x1400180f3  lea     edx, [rbx+0Ah]
0x1400180f6  lea     r8, WPP_b2c5afd6f6c2384decec4e1014c730bc_Traceguids
0x1400180fd  call    WPP_SF_
0x140018102  mov     eax, 0C000009Ah
0x140018107  jmp     loc_1400183C2
0x14001810c  mov     edi, 1
0x140018111  lea     rcx, [rax+78h]; SpinLock
0x140018115  mov     [rax+80h], edi
0x14001811b  call    cs:__imp_KeInitializeSpinLock
0x140018122  nop     dword ptr [rax+rax+00h]
0x140018127  lea     rbp, [rbx+10h]
0x14001812b  mov     rcx, rbp; Resource
0x14001812e  call    cs:__imp_ExInitializeResourceLite
0x140018135  nop     dword ptr [rax+rax+00h]
0x14001813a  movups  xmm0, xmmword ptr [rsi]
0x14001813d  lea     rcx, [rbx+0F0h]; void *
0x140018144  movups  xmmword ptr [rbx+88h], xmm0
0x14001814b  movups  xmm1, xmmword ptr [rsi+10h]
0x14001814f  movups  xmmword ptr [rbx+98h], xmm1
0x140018156  movups  xmm0, xmmword ptr [rsi+20h]
0x14001815a  movups  xmmword ptr [rbx+0A8h], xmm0
0x140018161  movups  xmm1, xmmword ptr [rsi+30h]
0x140018165  movups  xmmword ptr [rbx+0B8h], xmm1
0x14001816c  movups  xmm0, xmmword ptr [rsi+40h]
0x140018170  movups  xmmword ptr [rbx+0C8h], xmm0
0x140018177  movups  xmm1, xmmword ptr [rsi+50h]
0x14001817b  movups  xmmword ptr [rbx+0D8h], xmm1
0x140018182  mov     [rbx+90h], rcx
0x140018189  movzx   r8d, word ptr [rsi]; Size
0x14001818d  mov     rdx, [rsi+8]; Src
0x140018191  call    memmove
0x140018196  call    cs:__imp_KeEnterCriticalRegion
0x14001819d  nop     dword ptr [rax+rax+00h]
0x1400181a2  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x1400181a9  mov     dl, dil; Wait
0x1400181ac  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400181b3  nop     dword ptr [rax+rax+00h]
0x1400181b8  mov     rcx, cs:SrvNetDeviceExtension
0x1400181bf  add     rcx, 68h ; 'h'; SpinLock
0x1400181c3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400181ca  nop     dword ptr [rax+rax+00h]
0x1400181cf  mov     rdx, cs:SrvNetDeviceExtension
0x1400181d6  lea     r9d, [rdi+6]
0x1400181da  mov     r8b, al
0x1400181dd  cmp     [rdx+208h], r9d
0x1400181e4  jl      loc_140018289
0x1400181ea  lea     rcx, [rdx+68h]; SpinLock
0x1400181ee  mov     dl, al; NewIrql
0x1400181f0  call    cs:__imp_KeReleaseSpinLock
0x1400181f7  nop     dword ptr [rax+rax+00h]
0x1400181fc  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x140018203  call    cs:__imp_ExReleaseResourceLite
0x14001820a  nop     dword ptr [rax+rax+00h]
0x14001820f  call    cs:__imp_KeLeaveCriticalRegion
0x140018216  nop     dword ptr [rax+rax+00h]
0x14001821b  mov     rcx, rbp; Resource
0x14001821e  call    cs:__imp_ExDeleteResourceLite
0x140018225  nop     dword ptr [rax+rax+00h]
0x14001822a  mov     ecx, [rbx-0Ch]
0x14001822d  xor     r8d, r8d
0x140018230  mov     edx, [rbx-10h]
0x140018233  call    SrvNetUpdateMemStatistics
0x140018238  xor     edx, edx; Tag
0x14001823a  lea     rcx, [rbx-10h]; P
0x14001823e  call    cs:__imp_ExFreePoolWithTag
0x140018245  nop     dword ptr [rax+rax+00h]
0x14001824a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140018251  lea     rax, WPP_GLOBAL_Control
0x140018258  cmp     rcx, rax
0x14001825b  jz      short loc_14001827F
0x14001825d  test    dword ptr [rcx+2Ch], 1000h
0x140018264  jz      short loc_14001827F
0x140018266  cmp     [rcx+29h], dil
0x14001826a  jb      short loc_14001827F
0x14001826c  mov     rcx, [rcx+18h]
0x140018270  lea     edx, [rdi+0Ah]
0x140018273  lea     r8, WPP_b2c5afd6f6c2384decec4e1014c730bc_Traceguids
0x14001827a  call    WPP_SF_
0x14001827f  mov     eax, 0C00000C1h
0x140018284  jmp     loc_1400183C2
0x140018289  xor     ecx, ecx
0x14001828b  movzx   eax, cx
0x14001828e  cmp     qword ptr [rdx+rax*8+1D0h], 0
0x140018297  jz      short loc_14001830A
0x140018299  add     cx, di
0x14001829c  cmp     cx, r9w
0x1400182a0  jb      short loc_14001828B
0x1400182a2  jnz     short loc_14001830A
0x1400182a4  lea     rcx, [rdx+68h]; SpinLock
0x1400182a8  mov     dl, r8b; NewIrql
0x1400182ab  call    cs:__imp_KeReleaseSpinLock
0x1400182b2  nop     dword ptr [rax+rax+00h]
0x1400182b7  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x1400182be  call    cs:__imp_ExReleaseResourceLite
0x1400182c5  nop     dword ptr [rax+rax+00h]
0x1400182ca  call    cs:__imp_KeLeaveCriticalRegion
0x1400182d1  nop     dword ptr [rax+rax+00h]
0x1400182d6  mov     rcx, rbp; Resource
0x1400182d9  call    cs:__imp_ExDeleteResourceLite
0x1400182e0  nop     dword ptr [rax+rax+00h]
0x1400182e5  mov     ecx, [rbx-0Ch]
0x1400182e8  xor     r8d, r8d
0x1400182eb  mov     edx, [rbx-10h]
0x1400182ee  call    SrvNetUpdateMemStatistics
0x1400182f3  xor     edx, edx; Tag
0x1400182f5  lea     rcx, [rbx-10h]; P
0x1400182f9  call    cs:__imp_ExFreePoolWithTag
0x140018300  nop     dword ptr [rax+rax+00h]
0x140018305  jmp     loc_14001827F
0x14001830a  movzx   eax, cx
0x14001830d  mov     [rbx+0E8h], eax
0x140018313  mov     dword ptr [rbx+84h], 0
0x14001831d  mov     byte ptr [rbx+0EDh], 0
0x140018324  add     [rdx+208h], edi
0x14001832a  movzx   eax, cx
0x14001832d  lea     rcx, [rdx+68h]; SpinLock
0x140018331  mov     [rdx+rax*8+1D0h], rbx
0x140018339  mov     dl, r8b; NewIrql
0x14001833c  mov     [r14], rbx
0x14001833f  call    cs:__imp_KeReleaseSpinLock
0x140018346  nop     dword ptr [rax+rax+00h]
0x14001834b  mov     rax, cs:SrvNetDeviceExtension
0x140018352  lock add [rax+70h], edi
0x140018356  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x14001835d  call    cs:__imp_ExReleaseResourceLite
0x140018364  nop     dword ptr [rax+rax+00h]
0x140018369  call    cs:__imp_KeLeaveCriticalRegion
0x140018370  nop     dword ptr [rax+rax+00h]
0x140018375  mov     r8b, dil
0x140018378  xor     edx, edx
0x14001837a  xor     ecx, ecx
0x14001837c  call    SrvNetTriggerScavenger
0x140018381  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140018388  lea     rax, WPP_GLOBAL_Control
0x14001838f  cmp     rcx, rax
0x140018392  jz      short loc_1400183C0
0x140018394  test    dword ptr [rcx+2Ch], 1000h
0x14001839b  jz      short loc_1400183C0
0x14001839d  cmp     byte ptr [rcx+29h], 2
0x1400183a1  jb      short loc_1400183C0
0x1400183a3  mov     rcx, [rcx+18h]
0x1400183a7  lea     r8, WPP_b2c5afd6f6c2384decec4e1014c730bc_Traceguids
0x1400183ae  mov     edx, 0Ch
0x1400183b3  mov     [rsp+58h+var_38], rbx
0x1400183b8  mov     r9, rsi
0x1400183bb  call    WPP_SF_Zq
0x1400183c0  xor     eax, eax
0x1400183c2  add     rsp, 30h
0x1400183c6  pop     r14
0x1400183c8  pop     rdi
0x1400183c9  pop     rsi
0x1400183ca  pop     rbp
0x1400183cb  pop     rbx
0x1400183cc  retn
```
