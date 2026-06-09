# MpRegHardenningBlockOperation

- ea: `0x14004ef30`
- end: `0x14004f599`
- name: `MpRegHardenningBlockOperation`
- size: `1641`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14004d0d0`

## callees

- `0x1400051bc`
- `0x14000d1e8`
- `0x1400118d0`
- `0x140030060`
- `0x140040388`
- `0x14004b6d0`
- `0x14004e5c0`
- `0x14004ef30`
- `0x14004f59c`
- `0x14004f6bc`
- `0x14004fe9c`
- `0x14006f618`
- `0x14007fb34`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14004f091`
- `ntoskrnl!PsGetProcessId` at `0x14004f091`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14004f2d2`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14004f2d2`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14004f07f`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14004f07f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f125`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f125`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f119`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f119`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004f0c2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004f0c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004f0b0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004f0b0`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004f06d`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004f06d`
- `ntoskrnl!IoThreadToProcess` at `0x14004f02c`
- `ntoskrnl!IoThreadToProcess` at `0x14004f058`
- `ntoskrnl!IoThreadToProcess` at `0x14004f02c`
- `ntoskrnl!IoThreadToProcess` at `0x14004f058`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f532`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f54b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f532`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f54b`

## string_xrefs

- `0x14004f399`: `[Mini-filter] Denied registry operation for key [%wZ] based on hardcode list. MonitorFlags: [0x%x] MonitorData: [0x%p]`
- `0x14004f4d4`: `[Mini-filter] Denied registry operation for key [%wZ] based on hardcode list. MonitorFlags: [0x%x] MonitorData: [0x%p]`

## pseudocode

```c
__int64 __fastcall MpRegHardenningBlockOperation(
        __int64 a1,
        __int64 a2,
        void *a3,
        const UNICODE_STRING *a4,
        PCUNICODE_STRING *a5,
        _BYTE *a6,
        _BYTE *a7)
{
  int KeyDestinationName; // r12d
  UNICODE_STRING *v8; // r13
  __int64 *v9; // rsi
  struct _KPROCESS *v11; // rbx
  struct _KPROCESS *v12; // rbx
  struct _KPROCESS *CurrentProcess; // rbx
  LONGLONG TimeQuadPart; // r12
  unsigned __int64 ProcessId; // rdi
  char *v16; // rbx
  volatile signed __int32 **v17; // r8
  volatile signed __int32 *i; // rax
  char IsMatch; // al
  __int64 v20; // rdx
  int KeyName; // eax
  unsigned __int64 v22; // rbx
  char v23; // al
  int v24; // [rsp+20h] [rbp-B8h]
  PCUNICODE_STRING v25[2]; // [rsp+48h] [rbp-90h] BYREF
  __int64 v26; // [rsp+58h] [rbp-80h]
  PVOID Object; // [rsp+60h] [rbp-78h]
  __int64 v28; // [rsp+68h] [rbp-70h]
  PCUNICODE_STRING SourceString; // [rsp+70h] [rbp-68h]
  PCUNICODE_STRING String2; // [rsp+78h] [rbp-60h] BYREF

  v26 = a1;
  SourceString = a4;
  KeyDestinationName = 0;
  Object = a3;
  v8 = 0;
  v28 = a2;
  String2 = 0;
  v9 = 0;
  v25[0] = 0;
  if ( !a3 )
  {
    if ( !a2 )
      goto LABEL_3;
LABEL_6:
    if ( !a5 || !a7 || !a6 )
      goto LABEL_3;
    *a7 = 0;
    *a6 = 0;
    *a5 = 0;
    if ( *(_DWORD *)(MpData + 2444) )
      return (unsigned int)KeyDestinationName;
    if ( *(_QWORD *)(MpData + 232)
      || (v22 = MEMORY[0xFFFFF78000000320], 0x861C46800uLL / KeQueryTimeIncrement() + *(_QWORD *)(MpData + 4032) >= v22) )
    {
      v11 = *(struct _KPROCESS **)(MpData + 232);
      if ( IoThreadToProcess(KeGetCurrentThread()) != v11 )
      {
        v12 = *(struct _KPROCESS **)(MpData + 256);
        if ( IoThreadToProcess(KeGetCurrentThread()) != v12 )
        {
          CurrentProcess = IoGetCurrentProcess();
          TimeQuadPart = PsGetProcessCreateTimeQuadPart(CurrentProcess);
          ProcessId = (unsigned __int64)PsGetProcessId(CurrentProcess);
          if ( ProcessId )
          {
            v16 = (char *)MpProcessTable;
            KeEnterCriticalRegion();
            ExAcquireResourceSharedLite((PERESOURCE)(v16 + 8), 1u);
            v17 = (volatile signed __int32 **)(*((_QWORD *)MpProcessTable + 48) + 16 * ((ProcessId >> 2) & 0x7F));
            for ( i = *v17; i != (volatile signed __int32 *)v17; i = *(volatile signed __int32 **)i )
            {
              if ( ProcessId == *((_QWORD *)i + 2) && TimeQuadPart == *((_QWORD *)i + 3) )
              {
                _InterlockedIncrement(i + 10);
                v9 = (__int64 *)(i - 2);
                break;
              }
            }
            ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
            KeLeaveCriticalRegion();
          }
          if ( (unsigned __int8)MpIsRegistryHardeningExemptByContext(v9) )
          {
            KeyDestinationName = 0;
            goto LABEL_23;
          }
          if ( Object )
          {
            KeyName = MpRegpGetKeyName(Object);
            KeyDestinationName = KeyName;
            if ( KeyName < 0 )
            {
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
              {
                goto LABEL_23;
              }
              v20 = 157;
              v24 = KeyName;
              goto LABEL_40;
            }
          }
          else
          {
            KeyDestinationName = MpRegpCheckExistingKey(v28, a6, &String2);
            if ( KeyDestinationName < 0 )
            {
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
              {
                goto LABEL_23;
              }
              v20 = 158;
              v24 = KeyDestinationName;
              goto LABEL_40;
            }
            if ( *a6 )
              goto LABEL_23;
          }
          IsMatch = MpRegHardeningIsMatch(String2);
          *a7 = IsMatch;
          if ( IsMatch )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
            {
              WPP_SF_ZDq(
                WPP_GLOBAL_Control->AttachedDevice,
                159,
                *(_DWORD *)(MpData + 868),
                (_DWORD)String2,
                *(_DWORD *)(MpData + 868),
                *((_QWORD *)MpRegData + 2));
            }
            MpLogPrintfW(
              L"[Mini-filter] Denied registry operation for key [%wZ] based on hardcode list. MonitorFlags: [0x%x] MonitorData: [0x%p]",
              String2,
              *(unsigned int *)(MpData + 868),
              *((_QWORD *)MpRegData + 2));
            MpTraceRegHardeningNotification(1, 0, (_DWORD)v9, v26, (__int64)String2, 0, 0);
            goto LABEL_23;
          }
          if ( SourceString )
          {
            if ( (*(_DWORD *)(MpData + 864) & 4) != 0
              || (KeyDestinationName = MpRegpCopyUnicodeString(SourceString), KeyDestinationName >= 0) )
            {
              KeyDestinationName = MpRegpGetKeyDestinationName(String2, SourceString, v25);
              if ( KeyDestinationName >= 0 )
              {
                v8 = (UNICODE_STRING *)v25[0];
                v23 = MpRegHardeningIsMatch(v25[0]);
                *a7 = v23;
                if ( v23 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                  {
                    WPP_SF_ZDq(
                      WPP_GLOBAL_Control->AttachedDevice,
                      162,
                      *(_DWORD *)(MpData + 868),
                      (_DWORD)v8,
                      *(_DWORD *)(MpData + 868),
                      *((_QWORD *)MpRegData + 2));
                  }
                  MpLogPrintfW(
                    L"[Mini-filter] Denied registry operation for key [%wZ] based on hardcode list. MonitorFlags: [0x%x] M"
                     "onitorData: [0x%p]",
                    v8,
                    *(unsigned int *)(MpData + 868),
                    *((_QWORD *)MpRegData + 2));
                  MpTraceRegHardeningNotification(1, 0, (_DWORD)v9, v26, (__int64)String2, 0, 0);
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                {
                  _mm_lfence();
                  WPP_SF_qD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    161,
                    WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
                    KeGetCurrentThread(),
                    KeyDestinationName);
                }
                v8 = (UNICODE_STRING *)v25[0];
              }
              goto LABEL_23;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              v20 = 160;
              v24 = KeyDestinationName;
LABEL_40:
              _mm_lfence();
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                v20,
                WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
                KeGetCurrentThread(),
                v24);
            }
          }
        }
      }
    }
LABEL_23:
    if ( String2 )
    {
      *a5 = String2;
      String2 = 0;
    }
    if ( v8 )
      ExFreePoolWithTag(v8, 0x4B72504Du);
    if ( v9 )
      MpReleaseProcessContext(v9);
    return (unsigned int)KeyDestinationName;
  }
  if ( !a2 )
    goto LABEL_6;
LABEL_3:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      156,
      WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
      KeGetCurrentThread(),
      -1073741811);
  return 3221225485LL;
}

```

## disassembly

```asm
0x14004ef30  push    rbp
0x14004ef32  push    rsi
0x14004ef33  push    rdi
0x14004ef34  push    r12
0x14004ef36  push    r13
0x14004ef38  push    r14
0x14004ef3a  push    r15
0x14004ef3c  sub     rsp, 0A0h
0x14004ef43  mov     rax, cs:__security_cookie
0x14004ef4a  xor     rax, rsp
0x14004ef4d  mov     [rsp+0D8h+var_58], rax
0x14004ef55  mov     r14, [rsp+0D8h+arg_20]
0x14004ef5d  mov     r15, [rsp+0D8h+arg_28]
0x14004ef65  mov     rbp, [rsp+0D8h+arg_30]
0x14004ef6d  mov     [rsp+0D8h+var_80], rcx
0x14004ef72  xor     ecx, ecx
0x14004ef74  mov     [rsp+0D8h+SourceString], r9
0x14004ef79  mov     r12d, ecx
0x14004ef7c  mov     [rsp+0D8h+Object], r8
0x14004ef81  mov     r13d, ecx
0x14004ef84  mov     [rsp+0D8h+var_70], rdx
0x14004ef89  mov     edi, ecx
0x14004ef8b  mov     [rsp+0D8h+String2], rcx
0x14004ef90  mov     esi, ecx
0x14004ef92  mov     [rsp+0D8h+var_90], rcx
0x14004ef97  mov     [rsp+0D8h+var_98], rcx
0x14004ef9c  test    r8, r8
0x14004ef9f  jz      short loc_14004EFC7
0x14004efa1  test    rdx, rdx
0x14004efa4  jz      short loc_14004EFCC
0x14004efa6  mov     rax, cs:WPP_GLOBAL_Control
0x14004efad  lea     rcx, WPP_GLOBAL_Control
0x14004efb4  cmp     rax, rcx
0x14004efb7  jnz     loc_14004F55C
0x14004efbd  mov     eax, 0C000000Dh
0x14004efc2  jmp     loc_14004F185
0x14004efc7  test    rdx, rdx
0x14004efca  jz      short loc_14004EFA6
0x14004efcc  test    r14, r14
0x14004efcf  jz      short loc_14004EFA6
0x14004efd1  test    rbp, rbp
0x14004efd4  jz      short loc_14004EFA6
0x14004efd6  test    r15, r15
0x14004efd9  jz      short loc_14004EFA6
0x14004efdb  mov     [rbp+0], cl
0x14004efde  mov     [r15], cl
0x14004efe1  mov     [r14], rcx
0x14004efe4  mov     rax, cs:MpData
0x14004efeb  mov     ecx, [rax+98Ch]
0x14004eff1  test    ecx, ecx
0x14004eff3  jnz     loc_14004F182
0x14004eff9  mov     rax, cs:MpData
0x14004f000  mov     [rsp+0D8h+var_40], rbx
0x14004f008  cmp     [rax+0E8h], rsi
0x14004f00f  jz      loc_14004F2C5
0x14004f015  mov     rcx, gs:188h; Thread
0x14004f01e  mov     rax, cs:MpData
0x14004f025  mov     rbx, [rax+0E8h]
0x14004f02c  call    cs:__imp_IoThreadToProcess
0x14004f033  nop     dword ptr [rax+rax+00h]
0x14004f038  cmp     rax, rbx
0x14004f03b  jz      loc_14004F145
0x14004f041  mov     rcx, gs:188h; Thread
0x14004f04a  mov     rax, cs:MpData
0x14004f051  mov     rbx, [rax+100h]
0x14004f058  call    cs:__imp_IoThreadToProcess
0x14004f05f  nop     dword ptr [rax+rax+00h]
0x14004f064  cmp     rax, rbx
0x14004f067  jz      loc_14004F145
0x14004f06d  call    cs:__imp_IoGetCurrentProcess
0x14004f074  nop     dword ptr [rax+rax+00h]
0x14004f079  mov     rcx, rax; Process
0x14004f07c  mov     rbx, rax
0x14004f07f  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14004f086  nop     dword ptr [rax+rax+00h]
0x14004f08b  mov     rcx, rbx; Process
0x14004f08e  mov     r12, rax
0x14004f091  call    cs:__imp_PsGetProcessId
0x14004f098  nop     dword ptr [rax+rax+00h]
0x14004f09d  mov     rdi, rax
0x14004f0a0  test    rax, rax
0x14004f0a3  jz      loc_14004F131
0x14004f0a9  mov     rbx, cs:MpProcessTable
0x14004f0b0  call    cs:__imp_KeEnterCriticalRegion
0x14004f0b7  nop     dword ptr [rax+rax+00h]
0x14004f0bc  mov     dl, 1; Wait
0x14004f0be  lea     rcx, [rbx+8]; Resource
0x14004f0c2  call    cs:__imp_ExAcquireResourceSharedLite
0x14004f0c9  nop     dword ptr [rax+rax+00h]
0x14004f0ce  mov     rax, cs:MpProcessTable
0x14004f0d5  mov     r8, rdi
0x14004f0d8  shr     r8, 2
0x14004f0dc  and     r8d, 7Fh
0x14004f0e0  shl     r8, 4
0x14004f0e4  add     r8, [rax+180h]
0x14004f0eb  mov     rax, [r8]
0x14004f0ee  xchg    ax, ax
0x14004f0f0  cmp     rax, r8
0x14004f0f3  jz      short loc_14004F10E
0x14004f0f5  cmp     rdi, [rax+10h]
0x14004f0f9  jz      short loc_14004F100
0x14004f0fb  mov     rax, [rax]
0x14004f0fe  jmp     short loc_14004F0F0
0x14004f100  cmp     r12, [rax+18h]
0x14004f104  jnz     short loc_14004F0FB
0x14004f106  lock inc dword ptr [rax+28h]
0x14004f10a  lea     rsi, [rax-8]
0x14004f10e  mov     rcx, cs:MpProcessTable
0x14004f115  add     rcx, 8; Resource
0x14004f119  call    cs:__imp_ExReleaseResourceLite
0x14004f120  nop     dword ptr [rax+rax+00h]
0x14004f125  call    cs:__imp_KeLeaveCriticalRegion
0x14004f12c  nop     dword ptr [rax+rax+00h]
0x14004f131  mov     rcx, rsi
0x14004f134  call    MpIsRegistryHardeningExemptByContext
0x14004f139  test    al, al
0x14004f13b  jz      short loc_14004F1A9
0x14004f13d  mov     r12d, r13d
0x14004f140  mov     rdi, [rsp+0D8h+var_98]
0x14004f145  mov     rax, [rsp+0D8h+String2]
0x14004f14a  mov     rbx, [rsp+0D8h+var_40]
0x14004f152  test    rax, rax
0x14004f155  jz      short loc_14004F163
0x14004f157  mov     [r14], rax
0x14004f15a  mov     [rsp+0D8h+String2], 0
0x14004f163  test    rdi, rdi
0x14004f166  jnz     loc_14004F52A
0x14004f16c  test    r13, r13
0x14004f16f  jnz     loc_14004F543
0x14004f175  test    rsi, rsi
0x14004f178  jz      short loc_14004F182
0x14004f17a  mov     rcx, rsi
0x14004f17d  call    MpReleaseProcessContext
0x14004f182  mov     eax, r12d
0x14004f185  mov     rcx, [rsp+0D8h+var_58]
0x14004f18d  xor     rcx, rsp; StackCookie
0x14004f190  call    __security_check_cookie
0x14004f195  add     rsp, 0A0h
0x14004f19c  pop     r15
0x14004f19e  pop     r14
0x14004f1a0  pop     r13
0x14004f1a2  pop     r12
0x14004f1a4  pop     rdi
0x14004f1a5  pop     rsi
0x14004f1a6  pop     rbp
0x14004f1a7  retn
0x14004f1a9  mov     rcx, [rsp+0D8h+Object]; Object
0x14004f1ae  test    rcx, rcx
0x14004f1b1  jnz     loc_14004F282
0x14004f1b7  mov     rcx, [rsp+0D8h+var_70]
0x14004f1bc  lea     r8, [rsp+0D8h+String2]
0x14004f1c1  mov     rdx, r15
0x14004f1c4  call    MpRegpCheckExistingKey
0x14004f1c9  mov     r12d, eax
0x14004f1cc  test    eax, eax
0x14004f1ce  js      loc_14004F311
0x14004f1d4  cmp     [r15], r13b
0x14004f1d7  jnz     loc_14004F140
0x14004f1dd  mov     rcx, [rsp+0D8h+String2]; String2
0x14004f1e2  call    MpRegHardeningIsMatch
0x14004f1e7  mov     [rbp+0], al
0x14004f1ea  test    al, al
0x14004f1ec  jnz     loc_14004F342
0x14004f1f2  mov     rbx, [rsp+0D8h+SourceString]
0x14004f1f7  test    rbx, rbx
0x14004f1fa  jz      loc_14004F140
0x14004f200  mov     rax, cs:MpData
0x14004f207  mov     ecx, [rax+360h]
0x14004f20d  test    cl, 4
0x14004f210  jnz     loc_14004F3F8
0x14004f216  lea     rdx, [rsp+0D8h+var_98]
0x14004f21b  mov     rcx, rbx; SourceString
0x14004f21e  call    MpRegpCopyUnicodeString
0x14004f223  mov     r12d, eax
0x14004f226  test    eax, eax
0x14004f228  jns     loc_14004F3E9
0x14004f22e  mov     rax, cs:WPP_GLOBAL_Control
0x14004f235  lea     rcx, WPP_GLOBAL_Control
0x14004f23c  cmp     rax, rcx
0x14004f23f  jz      loc_14004F140
0x14004f245  mov     eax, [rax+2Ch]
0x14004f248  test    al, 1
0x14004f24a  jz      loc_14004F140
0x14004f250  mov     edx, 0A0h
0x14004f255  mov     dword ptr [rsp+0D8h+var_B8], r12d
0x14004f25a  lfence
0x14004f25d  mov     r9, gs:188h
0x14004f266  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004f26d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f274  mov     rcx, [rcx+18h]
0x14004f278  call    WPP_SF_qD
0x14004f27d  jmp     loc_14004F140
0x14004f282  lea     rdx, [rsp+0D8h+String2]
0x14004f287  call    MpRegpGetKeyName
0x14004f28c  mov     r12d, eax
0x14004f28f  test    eax, eax
0x14004f291  jns     loc_14004F1DD
0x14004f297  mov     rdx, cs:WPP_GLOBAL_Control
0x14004f29e  lea     rcx, WPP_GLOBAL_Control
0x14004f2a5  cmp     rdx, rcx
0x14004f2a8  jz      loc_14004F140
0x14004f2ae  mov     ecx, [rdx+2Ch]
0x14004f2b1  test    cl, 4
0x14004f2b4  jz      loc_14004F140
0x14004f2ba  mov     edx, 9Dh
0x14004f2bf  mov     dword ptr [rsp+0D8h+var_B8], eax
0x14004f2c3  jmp     short loc_14004F25A
0x14004f2c5  mov     rbx, 0FFFFF78000000320h
0x14004f2cf  mov     rbx, [rbx]
0x14004f2d2  call    cs:__imp_KeQueryTimeIncrement
0x14004f2d9  nop     dword ptr [rax+rax+00h]
0x14004f2de  mov     ecx, eax
0x14004f2e0  xor     edx, edx
0x14004f2e2  mov     rax, 861C46800h
0x14004f2ec  div     rcx
0x14004f2ef  mov     r8, rax
0x14004f2f2  mov     rax, cs:MpData
0x14004f2f9  mov     rax, [rax+0FC0h]
0x14004f300  add     rax, r8
0x14004f303  cmp     rax, rbx
0x14004f306  jnb     loc_14004F015
0x14004f30c  jmp     loc_14004F145
0x14004f311  mov     rax, cs:WPP_GLOBAL_Control
0x14004f318  lea     rcx, WPP_GLOBAL_Control
0x14004f31f  cmp     rax, rcx
0x14004f322  jz      loc_14004F140
0x14004f328  mov     eax, [rax+2Ch]
0x14004f32b  test    al, 4
0x14004f32d  jz      loc_14004F140
0x14004f333  mov     edx, 9Eh
0x14004f338  mov     dword ptr [rsp+0D8h+var_B8], r12d
0x14004f33d  jmp     loc_14004F25A
0x14004f342  mov     rdx, cs:WPP_GLOBAL_Control
0x14004f349  lea     rcx, WPP_GLOBAL_Control
0x14004f350  cmp     rdx, rcx
0x14004f353  jz      short loc_14004F392
0x14004f355  mov     eax, [rdx+2Ch]
0x14004f358  test    al, 2
0x14004f35a  jz      short loc_14004F392
0x14004f35c  mov     rax, cs:MpRegData
0x14004f363  mov     rcx, [rdx+18h]
0x14004f367  mov     edx, 9Fh
0x14004f36c  mov     r8, [rax+10h]
0x14004f370  mov     rax, cs:MpData
0x14004f377  mov     [rsp+0D8h+var_B0], r8
0x14004f37c  mov     r8d, [rax+364h]
0x14004f383  mov     r9, [rsp+0D8h+String2]
0x14004f388  mov     dword ptr [rsp+0D8h+var_B8], r8d
0x14004f38d  call    WPP_SF_ZDq
0x14004f392  mov     r8, cs:MpData
0x14004f399  lea     rcx, aMiniFilterDeni_9; "[Mini-filter] Denied registry operation"...
0x14004f3a0  mov     rax, cs:MpRegData
0x14004f3a7  mov     r8d, [r8+364h]
0x14004f3ae  mov     rdx, [rsp+0D8h+String2]
0x14004f3b3  mov     r9, [rax+10h]
0x14004f3b7  call    MpLogPrintfW
0x14004f3bc  mov     rax, [rsp+0D8h+String2]
0x14004f3c1  mov     r8, rsi
0x14004f3c4  mov     r9, [rsp+0D8h+var_80]
0x14004f3c9  xor     edx, edx
0x14004f3cb  mov     [rsp+0D8h+var_A8], r13
0x14004f3d0  mov     ecx, 1
0x14004f3d5  mov     [rsp+0D8h+var_B0], r13
0x14004f3da  mov     [rsp+0D8h+var_B8], rax
0x14004f3df  call    MpTraceRegHardeningNotification
0x14004f3e4  jmp     loc_14004F140
0x14004f3e9  mov     rdi, [rsp+0D8h+var_98]
0x14004f3ee  test    rdi, rdi
0x14004f3f1  jz      short loc_14004F3FD
0x14004f3f3  mov     rbx, rdi
0x14004f3f6  jmp     short loc_14004F3FD
0x14004f3f8  mov     rdi, [rsp+0D8h+var_98]
0x14004f3fd  mov     rcx, [rsp+0D8h+String2]
0x14004f402  lea     r8, [rsp+0D8h+var_90]
0x14004f407  mov     rdx, rbx
0x14004f40a  call    MpRegpGetKeyDestinationName
0x14004f40f  mov     r12d, eax
0x14004f412  test    eax, eax
0x14004f414  jns     short loc_14004F467
0x14004f416  mov     rax, cs:WPP_GLOBAL_Control
0x14004f41d  lea     rcx, WPP_GLOBAL_Control
0x14004f424  cmp     rax, rcx
0x14004f427  jz      short loc_14004F45D
0x14004f429  mov     eax, [rax+2Ch]
0x14004f42c  test    al, 1
0x14004f42e  jz      short loc_14004F45D
0x14004f430  lfence
0x14004f433  mov     r9, gs:188h
0x14004f43c  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004f443  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f44a  mov     edx, 0A1h
0x14004f44f  mov     dword ptr [rsp+0D8h+var_B8], r12d
0x14004f454  mov     rcx, [rcx+18h]
0x14004f458  call    WPP_SF_qD
0x14004f45d  mov     r13, [rsp+0D8h+var_90]
0x14004f462  jmp     loc_14004F145
0x14004f467  mov     r13, [rsp+0D8h+var_90]
0x14004f46c  mov     rcx, r13; String2
0x14004f46f  call    MpRegHardeningIsMatch
0x14004f474  mov     [rbp+0], al
  ... truncated ...
```
