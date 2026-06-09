# UdfCommonDevControl

- ea: `0x140054830`
- end: `0x140054d61`
- name: `UdfCommonDevControl`
- size: `1329`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400077f0`
- `0x1400094c0`

## callees

- `0x1400030e0`
- `0x14000a0ec`
- `0x14000a2e8`
- `0x14000ca54`
- `0x14000cad4`
- `0x1400318f4`
- `0x1400319f8`
- `0x140031d9c`
- `0x14003aa44`
- `0x1400444c4`
- `0x140045f10`
- `0x14004ce50`
- `0x140054830`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140054c65`
- `ntoskrnl!ExReleaseResourceLite` at `0x140054cfe`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ac05`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ac30`
- `ntoskrnl!ExReleaseResourceLite` at `0x140054c65`
- `ntoskrnl!ExReleaseResourceLite` at `0x140054cfe`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ac05`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ac30`
- `ntoskrnl!IoIs32bitProcess` at `0x140054926`
- `ntoskrnl!IoIs32bitProcess` at `0x140054926`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140054a85`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140054a85`
- `ntoskrnl!IofCallDriver` at `0x1400549c6`
- `ntoskrnl!IofCallDriver` at `0x1400549c6`

## pseudocode

```c
__int64 __fastcall UdfCommonDevControl(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  __int64 v4; // rdi
  char v5; // r12
  bool v6; // r13
  __int64 v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // r15
  unsigned __int64 v12; // r8
  unsigned int Structure; // ebx
  int v14; // edx
  char *v15; // rdi
  bool v16; // zf
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // r8
  unsigned __int64 v21; // rax
  __int64 v22; // rcx
  char v23; // al
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // rcx
  __int64 v28; // [rsp+70h] [rbp+8h]
  unsigned __int64 v29; // [rsp+78h] [rbp+10h]

  v2 = a2;
  v4 = *(_QWORD *)(a1 + 16);
  v5 = 0;
  v6 = (*(_DWORD *)(v4 + 48) & 0x202000) != 0;
  v7 = *(_QWORD *)(a2 + 184);
  v28 = v7;
  v8 = *(_QWORD *)(v7 + 48);
  v9 = *(_QWORD *)(v8 + 32);
  v10 = v9 & 7;
  *(_QWORD *)(v8 + 32) = v9;
  if ( (v9 & 7) != 0 )
  {
    v11 = *(_QWORD *)(v8 + 24);
    v12 = v9 & 0xFFFFFFFFFFFFFFF8uLL;
    v29 = v12;
    Structure = 0;
  }
  else
  {
    Structure = 0;
    v11 = 0;
    v12 = 0;
    v29 = 0;
  }
  if ( v10 == 4 )
  {
    UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(v11 + 136) + 80LL) + 8LL, 0, 1);
    UdfVerifyScbOperation(a1, v11, v29);
    if ( v6 )
    {
      UdfAcquireDeviceShared(a1, v4, 0);
      v5 = 1;
    }
    if ( *(_DWORD *)(v28 + 24) != 2966528 )
    {
      if ( *(_DWORD *)(v28 + 24) == 3362820 || *(_DWORD *)(v28 + 24) == 3362824 )
      {
        Structure = UdfDvdTransferKey(a1, v2, v11);
      }
      else
      {
        v24 = v2;
        v25 = a1;
        if ( *(_DWORD *)(v28 + 24) != 3363136 )
        {
          Structure = -1073741811;
          v26 = 3221225485LL;
LABEL_66:
          UdfCompleteRequest(v25, v24, v26);
          goto LABEL_67;
        }
        Structure = UdfDvdReadStructure(a1, v2, v11);
      }
LABEL_67:
      if ( v5 )
        UdfReleaseDevice(v27, v4, 0);
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v11 + 136) + 80LL) + 8LL));
      return Structure;
    }
    v26 = 0;
    v24 = v2;
    v25 = a1;
    goto LABEL_66;
  }
  if ( v10 != 2 )
  {
    Structure = -1073741811;
    v19 = 3221225485LL;
LABEL_28:
    UdfCompleteRequest(a1, a2, v19);
    return Structure;
  }
  v14 = *(_DWORD *)(v7 + 24);
  if ( v14 == 5488640 )
  {
    UdfCompleteRequest(a1, v2, 3221225659LL);
    return 3221225659LL;
  }
  else if ( v14 == 131136 )
  {
    UdfVerifyVcb(a1, *(_QWORD *)(*(_QWORD *)(v11 + 136) + 8LL), v12);
    if ( *(_DWORD *)(v28 + 8) >= 4u )
    {
      **(_DWORD **)(v2 + 24) = 2;
      *(_QWORD *)(v2 + 56) = 4;
      UdfCompleteRequest(a1, v2, 0);
      return 0;
    }
    else
    {
      UdfCompleteRequest(a1, v2, 3221225507LL);
      return 3221225507LL;
    }
  }
  else
  {
    if ( (v14 == 149512 || v14 == 2967560 || v14 == 477192) && (*(_DWORD *)(v4 + 48) & 0x2000000) != 0 )
    {
      UdfAcquireResource(a1, v4 + 1480, 0, 0);
      if ( *(_DWORD *)(v4 + 52) == 2 && (*(_DWORD *)(v4 + 2128) & 0x16) == 0x10 )
      {
        if ( (*(_DWORD *)(v4 + 48) & 0x200000) != 0 )
        {
          FsRtlNotifyVolumeEvent(*(PFILE_OBJECT *)(v28 + 48), 0xCu);
          UdfSeqCacheCloseSession(a1);
        }
        else
        {
          UdfStopBackgroundFormat(a1, v4);
        }
      }
      ExReleaseResourceLite((PERESOURCE)(v4 + 1480));
      goto LABEL_23;
    }
    if ( v14 == 315396
      || (v21 = (unsigned int)(v14 - 315412), (unsigned int)v21 <= 0x34)
      && (v22 = 0x11000000000001LL, _bittest64(&v22, v21)) )
    {
      if ( ((*(_DWORD *)(*(_QWORD *)(v7 + 48) + 80LL) & 0x1000) == 0 || (*(_DWORD *)(v12 + 4) & 0x1000) == 0)
        && *(_QWORD *)(v2 + 24) )
      {
        v15 = 0;
        v16 = IoIs32bitProcess((PIRP)v2) == 0;
        v17 = *(_DWORD *)(v28 + 24) - 315396;
        if ( v16 )
        {
          if ( (v17 & 0xFFFFFFEF) != 0 )
          {
            if ( *(_DWORD *)(v28 + 16) >= 0x40u )
              v15 = (char *)(*(_QWORD *)(v2 + 24) + 56LL);
          }
          else if ( *(_DWORD *)(v28 + 16) >= 0x38u )
          {
            v15 = (char *)(*(_QWORD *)(v2 + 24) + 36LL);
          }
        }
        else if ( (v17 & 0xFFFFFFEF) != 0 )
        {
          if ( *(_DWORD *)(v28 + 16) >= 0x34u )
            v15 = (char *)(*(_QWORD *)(v2 + 24) + 48LL);
        }
        else if ( *(_DWORD *)(v28 + 16) >= 0x2Cu )
        {
          v15 = (char *)(*(_QWORD *)(v2 + 24) + 28LL);
        }
        while ( Structure < 0xC )
        {
          if ( v15 && *v15 == *((_BYTE *)UdfDestructiveScsiOps + Structure) )
          {
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20) != 0 )
            {
              WPP_SF_q(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                10,
                WPP_97b62f4fd4923e954d92c3bcdfbe7fc1_Traceguids,
                *(_QWORD *)(a1 + 16));
            }
            v23 = *v15;
            if ( *v15 == 91 || v23 == -95 || v23 == 4 )
            {
              if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20) != 0 )
              {
                WPP_SF_(
                  *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                  11,
                  WPP_97b62f4fd4923e954d92c3bcdfbe7fc1_Traceguids);
              }
              *(_DWORD *)(v29 + 4) |= 0x1000u;
            }
            *(_DWORD *)(*(_QWORD *)(v28 + 48) + 80LL) |= 0x1000u;
            goto LABEL_23;
          }
          ++Structure;
        }
        goto LABEL_23;
      }
    }
    if ( v14 != 508004
      || (*(_DWORD *)(v4 + 48) & 1) != 0
      || (*(_BYTE *)(v7 + 2) & 0x10) != 0
      || (*(_DWORD *)(v12 + 4) & 8) != 0 )
    {
LABEL_23:
      if ( v6 )
      {
        UdfAcquireDeviceShared(a1, *(_QWORD *)(a1 + 16), 0);
        v5 = 1;
      }
      ++*(_BYTE *)(v2 + 67);
      *(_QWORD *)(v2 + 184) += 72LL;
      Structure = IofCallDriver(*(PDEVICE_OBJECT *)(*(_QWORD *)(a1 + 16) + 24LL), (PIRP)v2);
      if ( v5 )
        UdfReleaseDevice(v18, *(_QWORD *)(a1 + 16), 0);
      v19 = 0;
      a2 = 0;
      goto LABEL_28;
    }
    UdfCompleteRequest(a1, v2, 3221225506LL);
    return 3221225506LL;
  }
}

```

## disassembly

```asm
0x140054830  push    rbx
0x140054832  push    rsi
0x140054833  push    rdi
0x140054834  push    r12
0x140054836  push    r13
0x140054838  push    r14
0x14005483a  push    r15
0x14005483c  sub     rsp, 30h
0x140054840  mov     r14, rdx
0x140054843  mov     rsi, rcx
0x140054846  mov     rdi, [rcx+10h]
0x14005484a  mov     [rsp+68h+arg_18], rdi
0x140054852  xor     r13b, r13b
0x140054855  xor     r12b, r12b
0x140054858  mov     [rsp+68h+var_48], r12b
0x14005485d  test    dword ptr [rdi+30h], 202000h
0x140054864  jz      short loc_140054869
0x140054866  mov     r13b, 1
0x140054869  mov     r9, [rdx+0B8h]
0x140054870  mov     [rsp+68h+arg_0], r9
0x140054875  mov     rcx, [r9+30h]
0x140054879  mov     r8, [rcx+20h]
0x14005487d  mov     eax, r8d
0x140054880  and     eax, 7
0x140054883  mov     [rcx+20h], r8
0x140054887  jz      loc_140054B7E
0x14005488d  mov     r15, [rcx+18h]
0x140054891  mov     [rsp+68h+arg_10], r15
0x140054899  and     r8, 0FFFFFFFFFFFFFFF8h
0x14005489d  mov     [rsp+68h+arg_8], r8
0x1400548a2  xor     ebx, ebx
0x1400548a4  cmp     eax, 4
0x1400548a7  jz      loc_140054B98
0x1400548ad  cmp     eax, 2
0x1400548b0  jnz     loc_140054B71
0x1400548b6  mov     edx, [r9+18h]
0x1400548ba  cmp     edx, 53C000h
0x1400548c0  jz      loc_140054C76
0x1400548c6  cmp     edx, 20040h
0x1400548cc  jz      loc_140054C91
0x1400548d2  cmp     edx, 24808h
0x1400548d8  jz      loc_140054A2D
0x1400548de  cmp     edx, 2D4808h
0x1400548e4  jz      loc_140054A2D
0x1400548ea  cmp     edx, 74808h
0x1400548f0  jz      loc_140054A2D
0x1400548f6  cmp     edx, 4D004h
0x1400548fc  jnz     loc_140054A05
0x140054902  mov     rax, [r9+30h]
0x140054906  test    dword ptr [rax+50h], 1000h
0x14005490d  jz      short loc_140054919
0x14005490f  test    dword ptr [r8+4], 1000h
0x140054917  jnz     short loc_14005498C
0x140054919  cmp     qword ptr [r14+18h], 0
0x14005491e  jz      short loc_14005498C
0x140054920  mov     rdi, rbx
0x140054923  mov     rcx, r14; Irp
0x140054926  call    cs:__imp_IoIs32bitProcess
0x14005492d  nop     dword ptr [rax+rax+00h]
0x140054932  mov     r15, [rsp+68h+arg_0]
0x140054937  mov     ecx, [r15+18h]
0x14005493b  test    al, al
0x14005493d  lea     eax, [rcx-4D004h]
0x140054943  jnz     loc_140054AA0
0x140054949  test    eax, 0FFFFFFEFh
0x14005494e  jnz     loc_140054AD7
0x140054954  cmp     dword ptr [r15+10h], 38h ; '8'
0x140054959  jb      short loc_140054963
0x14005495b  mov     rdi, [r14+18h]
0x14005495f  add     rdi, 24h ; '$'
0x140054963  lea     rcx, UdfDestructiveScsiOps
0x14005496a  nop     word ptr [rax+rax+00h]
0x140054970  cmp     ebx, 0Ch
0x140054973  jnb     short loc_140054998
0x140054975  test    rdi, rdi
0x140054978  jz      short loc_140054988
0x14005497a  mov     eax, ebx
0x14005497c  movzx   eax, byte ptr [rax+rcx]
0x140054980  cmp     [rdi], al
0x140054982  jz      loc_140054AEF
0x140054988  inc     ebx
0x14005498a  jmp     short loc_140054970
0x14005498c  cmp     edx, 7C064h
0x140054992  jz      loc_140054D24
0x140054998  test    r13b, r13b
0x14005499b  jz      short loc_1400549AF
0x14005499d  xor     r8d, r8d
0x1400549a0  mov     rdx, [rsi+10h]
0x1400549a4  mov     rcx, rsi
0x1400549a7  call    UdfAcquireDeviceShared
0x1400549ac  mov     r12b, 1
0x1400549af  inc     byte ptr [r14+43h]
0x1400549b3  add     qword ptr [r14+0B8h], 48h ; 'H'
0x1400549bb  mov     rcx, [rsi+10h]
0x1400549bf  mov     rdx, r14; Irp
0x1400549c2  mov     rcx, [rcx+18h]; DeviceObject
0x1400549c6  call    cs:__imp_IofCallDriver
0x1400549cd  nop     dword ptr [rax+rax+00h]
0x1400549d2  mov     ebx, eax
0x1400549d4  test    r12b, r12b
0x1400549d7  jz      short loc_1400549E5
0x1400549d9  xor     r8d, r8d
0x1400549dc  mov     rdx, [rsi+10h]
0x1400549e0  call    UdfReleaseDevice
0x1400549e5  xor     r8d, r8d
0x1400549e8  xor     edx, edx
0x1400549ea  mov     rcx, rsi
0x1400549ed  call    UdfCompleteRequest
0x1400549f2  mov     eax, ebx
0x1400549f4  add     rsp, 30h
0x1400549f8  pop     r15
0x1400549fa  pop     r14
0x1400549fc  pop     r13
0x1400549fe  pop     r12
0x140054a00  pop     rdi
0x140054a01  pop     rsi
0x140054a02  pop     rbx
0x140054a03  retn
0x140054a05  lea     eax, [rdx-4D014h]
0x140054a0b  cmp     eax, 34h ; '4'
0x140054a0e  ja      loc_14005498C
0x140054a14  mov     rcx, 11000000000001h
0x140054a1e  bt      rcx, rax
0x140054a22  jnb     loc_14005498C
0x140054a28  jmp     loc_140054902
0x140054a2d  mov     eax, [rdi+30h]
0x140054a30  bt      eax, 19h
0x140054a34  jnb     loc_1400548F6
0x140054a3a  xor     r9d, r9d
0x140054a3d  xor     r8d, r8d
0x140054a40  lea     rdx, [rdi+5C8h]
0x140054a47  mov     rcx, rsi
0x140054a4a  call    UdfAcquireResource
0x140054a4f  nop
0x140054a50  cmp     dword ptr [rdi+34h], 2
0x140054a54  jnz     loc_140054CF7
0x140054a5a  mov     eax, [rdi+850h]
0x140054a60  and     al, 16h
0x140054a62  cmp     al, 10h
0x140054a64  jnz     loc_140054CF7
0x140054a6a  mov     eax, [rdi+30h]
0x140054a6d  bt      eax, 15h
0x140054a71  jnb     loc_140054CEB
0x140054a77  mov     edx, 0Ch; EventCode
0x140054a7c  mov     rcx, [rsp+68h+arg_0]
0x140054a81  mov     rcx, [rcx+30h]; FileObject
0x140054a85  call    cs:__imp_FsRtlNotifyVolumeEvent
0x140054a8c  nop     dword ptr [rax+rax+00h]
0x140054a91  xor     edx, edx
0x140054a93  mov     rcx, rsi
0x140054a96  call    UdfSeqCacheCloseSession
0x140054a9b  jmp     loc_140054CF7
0x140054aa0  test    eax, 0FFFFFFEFh
0x140054aa5  jz      short loc_140054ABF
0x140054aa7  cmp     dword ptr [r15+10h], 34h ; '4'
0x140054aac  jb      loc_140054963
0x140054ab2  mov     rdi, [r14+18h]
0x140054ab6  add     rdi, 30h ; '0'
0x140054aba  jmp     loc_140054963
0x140054abf  cmp     dword ptr [r15+10h], 2Ch ; ','
0x140054ac4  jb      loc_140054963
0x140054aca  mov     rdi, [r14+18h]
0x140054ace  add     rdi, 1Ch
0x140054ad2  jmp     loc_140054963
0x140054ad7  cmp     dword ptr [r15+10h], 40h ; '@'
0x140054adc  jb      loc_140054963
0x140054ae2  mov     rdi, [r14+18h]
0x140054ae6  add     rdi, 38h ; '8'
0x140054aea  jmp     loc_140054963
0x140054aef  lea     rbx, WPP_GLOBAL_Control
0x140054af6  mov     rcx, cs:WPP_GLOBAL_Control
0x140054afd  cmp     rcx, rbx
0x140054b00  jz      short loc_140054B22
0x140054b02  mov     eax, [rcx+2Ch]
0x140054b05  test    al, 20h
0x140054b07  jz      short loc_140054B22
0x140054b09  mov     edx, 0Ah
0x140054b0e  mov     r9, [rsi+10h]
0x140054b12  lea     r8, WPP_97b62f4fd4923e954d92c3bcdfbe7fc1_Traceguids
0x140054b19  mov     rcx, [rcx+18h]
0x140054b1d  call    WPP_SF_q
0x140054b22  movzx   eax, byte ptr [rdi]
0x140054b25  cmp     al, 5Bh ; '['
0x140054b27  jnz     loc_140054D0F
0x140054b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140054b34  cmp     rcx, rbx
0x140054b37  jz      short loc_140054B55
0x140054b39  mov     eax, [rcx+2Ch]
0x140054b3c  test    al, 20h
0x140054b3e  jz      short loc_140054B55
0x140054b40  mov     edx, 0Bh
0x140054b45  lea     r8, WPP_97b62f4fd4923e954d92c3bcdfbe7fc1_Traceguids
0x140054b4c  mov     rcx, [rcx+18h]
0x140054b50  call    WPP_SF_
0x140054b55  mov     rax, [rsp+68h+arg_8]
0x140054b5a  or      dword ptr [rax+4], 1000h
0x140054b61  mov     rax, [r15+30h]
0x140054b65  or      dword ptr [rax+50h], 1000h
0x140054b6c  jmp     loc_140054998
0x140054b71  mov     ebx, 0C000000Dh
0x140054b76  mov     r8d, ebx
0x140054b79  jmp     loc_1400549EA
0x140054b7e  xor     ebx, ebx
0x140054b80  mov     r15d, ebx
0x140054b83  mov     [rsp+68h+arg_10], rbx
0x140054b8b  mov     r8d, ebx
0x140054b8e  mov     [rsp+68h+arg_8], rbx
0x140054b93  jmp     loc_1400548A4
0x140054b98  mov     rax, [r15+88h]
0x140054b9f  mov     rdx, [rax+50h]
0x140054ba3  add     rdx, 8
0x140054ba7  mov     r9d, 1
0x140054bad  xor     r8d, r8d
0x140054bb0  mov     rcx, rsi
0x140054bb3  call    UdfAcquireResource
0x140054bb8  nop
0x140054bb9  mov     r8, [rsp+68h+arg_8]
0x140054bbe  mov     rdx, r15
0x140054bc1  mov     rcx, rsi
0x140054bc4  call    UdfVerifyScbOperation
0x140054bc9  test    r13b, r13b
0x140054bcc  jz      short loc_140054BE4
0x140054bce  xor     r8d, r8d
0x140054bd1  mov     rdx, rdi
0x140054bd4  mov     rcx, rsi
0x140054bd7  call    UdfAcquireDeviceShared
0x140054bdc  mov     r12b, 1
0x140054bdf  mov     [rsp+68h+var_48], r12b
0x140054be4  mov     rcx, [rsp+68h+arg_0]
0x140054be9  mov     ecx, [rcx+18h]
0x140054bec  sub     ecx, 2D4400h
0x140054bf2  jz      short loc_140054C37
0x140054bf4  sub     ecx, 60C04h
0x140054bfa  jz      short loc_140054C25
0x140054bfc  sub     ecx, 4
0x140054bff  jz      short loc_140054C25
0x140054c01  mov     rdx, r14
0x140054c04  cmp     ecx, 138h
0x140054c0a  mov     rcx, rsi
0x140054c0d  jz      short loc_140054C19
0x140054c0f  mov     ebx, 0C000000Dh
0x140054c14  mov     r8d, ebx
0x140054c17  jmp     short loc_140054C40
0x140054c19  mov     r8, r15
0x140054c1c  call    UdfDvdReadStructure
0x140054c21  mov     ebx, eax
0x140054c23  jmp     short loc_140054C46
0x140054c25  mov     r8, r15
0x140054c28  mov     rdx, r14
0x140054c2b  mov     rcx, rsi
0x140054c2e  call    UdfDvdTransferKey
0x140054c33  mov     ebx, eax
0x140054c35  jmp     short loc_140054C46
0x140054c37  xor     r8d, r8d
0x140054c3a  mov     rdx, r14
0x140054c3d  mov     rcx, rsi
0x140054c40  call    UdfCompleteRequest
0x140054c45  nop
0x140054c46  test    r12b, r12b
0x140054c49  jz      short loc_140054C56
0x140054c4b  xor     r8d, r8d
0x140054c4e  mov     rdx, rdi
0x140054c51  call    UdfReleaseDevice
0x140054c56  mov     rax, [r15+88h]
0x140054c5d  mov     rcx, [rax+50h]
0x140054c61  add     rcx, 8; Resource
0x140054c65  call    cs:__imp_ExReleaseResourceLite
0x140054c6c  nop     dword ptr [rax+rax+00h]
0x140054c71  jmp     loc_1400549F2
0x140054c76  mov     r8d, 0C00000BBh
0x140054c7c  mov     rdx, r14
0x140054c7f  mov     rcx, rsi
0x140054c82  call    UdfCompleteRequest
0x140054c87  mov     eax, 0C00000BBh
0x140054c8c  jmp     loc_1400549F4
0x140054c91  mov     rdx, [r15+88h]
0x140054c98  mov     rdx, [rdx+8]
0x140054c9c  mov     rcx, rsi
0x140054c9f  call    UdfVerifyVcb
0x140054ca4  mov     rcx, [rsp+68h+arg_0]
0x140054ca9  mov     rdx, r14
0x140054cac  cmp     dword ptr [rcx+8], 4
0x140054cb0  mov     rcx, rsi
0x140054cb3  jnb     short loc_140054CCA
0x140054cb5  mov     r8d, 0C0000023h
0x140054cbb  call    UdfCompleteRequest
0x140054cc0  mov     eax, 0C0000023h
0x140054cc5  jmp     loc_1400549F4
0x140054cca  mov     rax, [r14+18h]
0x140054cce  mov     dword ptr [rax], 2
0x140054cd4  mov     qword ptr [r14+38h], 4
0x140054cdc  xor     r8d, r8d
0x140054cdf  call    UdfCompleteRequest
0x140054ce4  xor     eax, eax
0x140054ce6  jmp     loc_1400549F4
0x140054ceb  mov     rdx, rdi
0x140054cee  mov     rcx, rsi
0x140054cf1  call    UdfStopBackgroundFormat
0x140054cf6  nop
0x140054cf7  lea     rcx, [rdi+5C8h]; Resource
  ... truncated ...
```
