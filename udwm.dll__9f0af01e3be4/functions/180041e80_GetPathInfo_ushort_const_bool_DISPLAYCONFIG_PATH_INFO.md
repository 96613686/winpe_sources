# GetPathInfo(ushort const *,bool,DISPLAYCONFIG_PATH_INFO *)

- ea: `0x180041e80`
- end: `0x18004209f`
- name: `?GetPathInfo@@YAJPEBG_NPEAUDISPLAYCONFIG_PATH_INFO@@@Z`
- size: `543`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, struct DISPLAYCONFIG_PATH_INFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180041ddc`

## callees

- `0x180017658`
- `0x180034580`
- `0x180041e80`
- `0x180095130`
- `0x180095b4c`

## import_xrefs

- `USER32!GetDisplayConfigBufferSizes` at `0x180041ee2`
- `USER32!GetDisplayConfigBufferSizes` at `0x180041ee2`
- `USER32!QueryDisplayConfig` at `0x180041f5a`
- `USER32!QueryDisplayConfig` at `0x180041f5a`
- `USER32!DisplayConfigGetDeviceInfo` at `0x180041fbc`
- `USER32!DisplayConfigGetDeviceInfo` at `0x180041fbc`

## pseudocode

```c
__int64 __fastcall GetPathInfo(
        const unsigned __int16 *a1,
        const struct std::nothrow_t *a2,
        struct DISPLAYCONFIG_PATH_INFO *a3)
{
  DISPLAYCONFIG_PATH_INFO *v4; // rbx
  DISPLAYCONFIG_MODE_INFO *v5; // rdi
  LONG DisplayConfigBufferSizes; // eax
  bool v8; // sf
  unsigned __int128 v9; // rax
  unsigned __int128 v10; // rax
  DISPLAYCONFIG_MODE_INFO *modeInfoArray; // rax
  int v12; // eax
  int v13; // r14d
  LONG DeviceInfo; // eax
  signed int v15; // esi
  const unsigned __int16 *v16; // rax
  int v17; // ecx
  UINT32 numPathArrayElements; // [rsp+30h] [rbp-69h] BYREF
  UINT32 numModeInfoArrayElements[3]; // [rsp+34h] [rbp-65h] BYREF
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+40h] [rbp-59h] BYREF
  char v22; // [rsp+54h] [rbp-45h] BYREF

  numPathArrayElements = 0;
  v4 = 0;
  numModeInfoArrayElements[0] = 0;
  v5 = 0;
  do
  {
    if ( v4 )
    {
      CDisplayBlackCurtainAnimatedVisual::operator delete(v4, a2);
      v4 = 0;
    }
    if ( v5 )
    {
      CDisplayBlackCurtainAnimatedVisual::operator delete(v5, a2);
      v5 = 0;
    }
    DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(2u, &numPathArrayElements, numModeInfoArrayElements);
    v8 = DisplayConfigBufferSizes < 0;
    if ( DisplayConfigBufferSizes > 0 )
      v8 = 1;
    if ( v8 )
      goto LABEL_28;
    v9 = numPathArrayElements * (unsigned __int128)0x48uLL;
    if ( !is_mul_ok(numPathArrayElements, 0x48u) )
      *(_QWORD *)&v9 = -1;
    v4 = (DISPLAYCONFIG_PATH_INFO *)operator new[](v9, *((const struct std::nothrow_t **)&v9 + 1));
    if ( !v4 )
      goto LABEL_28;
    v10 = numModeInfoArrayElements[0] * (unsigned __int128)0x40uLL;
    if ( !is_mul_ok(numModeInfoArrayElements[0], 0x40u) )
      *(_QWORD *)&v10 = -1;
    modeInfoArray = (DISPLAYCONFIG_MODE_INFO *)operator new[](v10, *((const struct std::nothrow_t **)&v10 + 1));
    v5 = modeInfoArray;
    if ( !modeInfoArray )
      goto LABEL_28;
    v12 = QueryDisplayConfig(2u, &numPathArrayElements, v4, numModeInfoArrayElements, modeInfoArray, 0);
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
  }
  while ( v12 == -2147024774 );
  if ( v12 < 0 )
    goto LABEL_28;
  v13 = 0;
  if ( !numPathArrayElements )
    goto LABEL_28;
  while ( 1 )
  {
    memset_0(&requestPacket, 0, 0x54u);
    requestPacket.type = DISPLAYCONFIG_DEVICE_INFO_GET_SOURCE_NAME;
    requestPacket.size = 84;
    requestPacket.adapterId = v4[v13].sourceInfo.adapterId;
    requestPacket.id = v4[v13].sourceInfo.id;
    DeviceInfo = DisplayConfigGetDeviceInfo(&requestPacket);
    v15 = DeviceInfo;
    if ( DeviceInfo > 0 )
      v15 = (unsigned __int16)DeviceInfo | 0x80070000;
    if ( v15 >= 0 )
    {
      v16 = a1;
      do
      {
        v17 = *(const unsigned __int16 *)((char *)v16 + &v22 - (char *)a1);
        a2 = (const struct std::nothrow_t *)((unsigned int)*v16 - v17);
        if ( (_DWORD)a2 )
          break;
        ++v16;
      }
      while ( v17 );
      if ( !(_DWORD)a2 )
        break;
    }
    if ( ++v13 >= numPathArrayElements )
      goto LABEL_28;
  }
  if ( v13 == -1 )
  {
LABEL_28:
    v15 = -2147024809;
    goto LABEL_29;
  }
  *(_OWORD *)&a3->sourceInfo.adapterId.LowPart = *(_OWORD *)&v4[v13].sourceInfo.adapterId.LowPart;
  *(_OWORD *)&a3->sourceInfo.statusFlags = *(_OWORD *)&v4[v13].sourceInfo.statusFlags;
  *(_OWORD *)&a3->targetInfo.modeInfoIdx = *(_OWORD *)&v4[v13].targetInfo.modeInfoIdx;
  *(_OWORD *)&a3->targetInfo.refreshRate.Numerator = *(_OWORD *)&v4[v13].targetInfo.refreshRate.Numerator;
  *(_QWORD *)&a3->targetInfo.statusFlags = *(_QWORD *)&v4[v13].targetInfo.statusFlags;
LABEL_29:
  if ( v4 )
    CDisplayBlackCurtainAnimatedVisual::operator delete(v4, a2);
  if ( v5 )
    CDisplayBlackCurtainAnimatedVisual::operator delete(v5, a2);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180041e80  push    rbp
0x180041e82  push    rbx
0x180041e83  push    rsi
0x180041e84  push    rdi
0x180041e85  push    r12
0x180041e87  push    r13
0x180041e89  push    r14
0x180041e8b  push    r15
0x180041e8d  lea     rbp, [rsp-1Fh]
0x180041e92  sub     rsp, 0B8h
0x180041e99  mov     rax, cs:__security_cookie
0x180041ea0  xor     rax, rsp
0x180041ea3  mov     [rbp+57h+var_50], rax
0x180041ea7  xor     esi, esi
0x180041ea9  mov     r15, r8
0x180041eac  mov     [rbp+57h+numPathArrayElements], esi
0x180041eaf  mov     ebx, esi
0x180041eb1  mov     [rbp+57h+numModeInfoArrayElements], esi
0x180041eb4  mov     edi, esi
0x180041eb6  or      r14, 0FFFFFFFFFFFFFFFFh
0x180041eba  mov     r13, rcx
0x180041ebd  mov     r12d, 80070000h
0x180041ec3  test    rbx, rbx
0x180041ec6  jnz     loc_18004207F
0x180041ecc  test    rdi, rdi
0x180041ecf  jnz     loc_18004208F
0x180041ed5  lea     r8, [rbp+57h+numModeInfoArrayElements]; numModeInfoArrayElements
0x180041ed9  mov     ecx, 2; flags
0x180041ede  lea     rdx, [rbp+57h+numPathArrayElements]; numPathArrayElements
0x180041ee2  call    cs:__imp_GetDisplayConfigBufferSizes
0x180041ee8  test    eax, eax
0x180041eea  jle     short loc_180041EF4
0x180041eec  movzx   eax, ax
0x180041eef  or      eax, r12d
0x180041ef2  test    eax, eax
0x180041ef4  js      loc_180041FFD
0x180041efa  mov     ecx, [rbp+57h+numPathArrayElements]
0x180041efd  mov     eax, 48h ; 'H'
0x180041f02  mul     rcx
0x180041f05  cmovb   rax, r14
0x180041f09  mov     rcx, rax; unsigned __int64
0x180041f0c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180041f11  mov     rbx, rax
0x180041f14  test    rax, rax
0x180041f17  jz      loc_180041FFD
0x180041f1d  mov     ecx, [rbp+57h+numModeInfoArrayElements]
0x180041f20  mov     eax, 40h ; '@'
0x180041f25  mul     rcx
0x180041f28  cmovb   rax, r14
0x180041f2c  mov     rcx, rax; unsigned __int64
0x180041f2f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180041f34  mov     rdi, rax
0x180041f37  test    rax, rax
0x180041f3a  jz      loc_180041FFD
0x180041f40  mov     [rsp+0F0h+currentTopologyId], rsi; currentTopologyId
0x180041f45  lea     r9, [rbp+57h+numModeInfoArrayElements]; numModeInfoArrayElements
0x180041f49  mov     r8, rbx; pathArray
0x180041f4c  mov     [rsp+0F0h+modeInfoArray], rax; modeInfoArray
0x180041f51  lea     rdx, [rbp+57h+numPathArrayElements]; numPathArrayElements
0x180041f55  mov     ecx, 2; flags
0x180041f5a  call    cs:__imp_QueryDisplayConfig
0x180041f60  test    eax, eax
0x180041f62  jle     short loc_180041F6A
0x180041f64  movzx   eax, ax
0x180041f67  or      eax, r12d
0x180041f6a  cmp     eax, 8007007Ah
0x180041f6f  jz      loc_180041EC3
0x180041f75  test    eax, eax
0x180041f77  js      loc_180041FFD
0x180041f7d  mov     r14d, esi
0x180041f80  cmp     [rbp+57h+numPathArrayElements], esi
0x180041f83  jbe     short loc_180041FFD
0x180041f85  xor     edx, edx; Val
0x180041f87  lea     rcx, [rbp+57h+requestPacket]; void *
0x180041f8b  lea     r8d, [rdx+54h]; Size
0x180041f8f  call    memset_0
0x180041f94  mov     eax, r14d
0x180041f97  mov     [rbp+57h+requestPacket.type], 1
0x180041f9e  mov     [rbp+57h+requestPacket.size], 54h ; 'T'
0x180041fa5  lea     rcx, [rax+rax*8]
0x180041fa9  mov     rax, [rbx+rcx*8]
0x180041fad  mov     qword ptr [rbp+57h+requestPacket.adapterId.LowPart], rax
0x180041fb1  mov     eax, [rbx+rcx*8+8]
0x180041fb5  lea     rcx, [rbp+57h+requestPacket]; requestPacket
0x180041fb9  mov     [rbp+57h+requestPacket.id], eax
0x180041fbc  call    cs:__imp_DisplayConfigGetDeviceInfo
0x180041fc2  mov     esi, eax
0x180041fc4  test    eax, eax
0x180041fc6  jle     short loc_180041FCE
0x180041fc8  movzx   esi, ax
0x180041fcb  or      esi, r12d
0x180041fce  test    esi, esi
0x180041fd0  js      short loc_180041FF4
0x180041fd2  lea     r8, [rbp+57h+var_9C]
0x180041fd6  mov     rax, r13
0x180041fd9  sub     r8, r13
0x180041fdc  movzx   edx, word ptr [rax]
0x180041fdf  movzx   ecx, word ptr [rax+r8]
0x180041fe4  sub     edx, ecx; struct std::nothrow_t *
0x180041fe6  jnz     short loc_180041FF0
0x180041fe8  add     rax, 2
0x180041fec  test    ecx, ecx
0x180041fee  jnz     short loc_180041FDC
0x180041ff0  test    edx, edx
0x180041ff2  jz      short loc_18004203E
0x180041ff4  inc     r14d
0x180041ff7  cmp     r14d, [rbp+57h+numPathArrayElements]
0x180041ffb  jb      short loc_180041F85
0x180041ffd  mov     esi, 80070057h
0x180042002  test    rbx, rbx
0x180042005  jz      short loc_18004200F
0x180042007  mov     rcx, rbx; void *
0x18004200a  call    ??3CDisplayBlackCurtainAnimatedVisual@@KAXPEAXAEBUnothrow_t@std@@@Z; CDisplayBlackCurtainAnimatedVisual::operator delete(void *,std::nothrow_t const &)
0x18004200f  test    rdi, rdi
0x180042012  jz      short loc_18004201C
0x180042014  mov     rcx, rdi; void *
0x180042017  call    ??3CDisplayBlackCurtainAnimatedVisual@@KAXPEAXAEBUnothrow_t@std@@@Z; CDisplayBlackCurtainAnimatedVisual::operator delete(void *,std::nothrow_t const &)
0x18004201c  mov     eax, esi
0x18004201e  mov     rcx, [rbp+57h+var_50]
0x180042022  xor     rcx, rsp; StackCookie
0x180042025  call    __security_check_cookie
0x18004202a  add     rsp, 0B8h
0x180042031  pop     r15
0x180042033  pop     r14
0x180042035  pop     r13
0x180042037  pop     r12
0x180042039  pop     rdi
0x18004203a  pop     rsi
0x18004203b  pop     rbx
0x18004203c  pop     rbp
0x18004203d  retn
0x18004203e  cmp     r14d, 0FFFFFFFFh
0x180042042  jz      short loc_180041FFD
0x180042044  movsxd  rax, r14d
0x180042047  lea     rcx, [rax+rax*8]
0x18004204b  movups  xmm0, xmmword ptr [rbx+rcx*8]
0x18004204f  movaps  xmmword ptr [r15], xmm0
0x180042053  movups  xmm1, xmmword ptr [rbx+rcx*8+10h]
0x180042058  movaps  xmmword ptr [r15+10h], xmm1
0x18004205d  movups  xmm0, xmmword ptr [rbx+rcx*8+20h]
0x180042062  movaps  xmmword ptr [r15+20h], xmm0
0x180042067  movups  xmm1, xmmword ptr [rbx+rcx*8+30h]
0x18004206c  movaps  xmmword ptr [r15+30h], xmm1
0x180042071  movsd   xmm0, qword ptr [rbx+rcx*8+40h]
0x180042077  movsd   qword ptr [r15+40h], xmm0
0x18004207d  jmp     short loc_180042002
0x18004207f  mov     rcx, rbx; void *
0x180042082  call    ??3CDisplayBlackCurtainAnimatedVisual@@KAXPEAXAEBUnothrow_t@std@@@Z; CDisplayBlackCurtainAnimatedVisual::operator delete(void *,std::nothrow_t const &)
0x180042087  mov     rbx, rsi
0x18004208a  jmp     loc_180041ECC
0x18004208f  mov     rcx, rdi; void *
0x180042092  call    ??3CDisplayBlackCurtainAnimatedVisual@@KAXPEAXAEBUnothrow_t@std@@@Z; CDisplayBlackCurtainAnimatedVisual::operator delete(void *,std::nothrow_t const &)
0x180042097  mov     rdi, rsi
0x18004209a  jmp     loc_180041ED5
```
