# WimAddToOverlayConfig

- ea: `0x14002ad28`
- end: `0x14002b01f`
- name: `WimAddToOverlayConfig`
- size: `759`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400263f0`

## callees

- `0x14000d3b8`
- `0x14000fce4`
- `0x1400116c0`
- `0x1400119c0`
- `0x14002ad28`
- `0x14002b43c`
- `0x14002b73c`
- `0x14002bdec`
- `0x14003c578`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002afc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002afde`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002aff8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002afc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002afde`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002aff8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002ae2d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002ae2d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002af9d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002af9d`
- `FLTMGR!FltClose` at `0x14002afb2`
- `FLTMGR!FltClose` at `0x14002afb2`

## pseudocode

```c
__int64 __fastcall WimAddToOverlayConfig(__int64 a1, int a2, int a3, int a4, int a5, _OWORD *a6, _QWORD *a7)
{
  char *PoolWithTag; // rsi
  int v8; // r13d
  int v10; // edi
  int v11; // eax
  _DWORD *v12; // r14
  size_t v13; // r15
  ULONG v14; // r12d
  char *v15; // rdi
  __int64 v16; // rbx
  unsigned int v17; // edx
  int v18; // r8d
  _OWORD *v19; // rax
  int v20; // eax
  int v21; // eax
  int v23; // [rsp+30h] [rbp-30h] BYREF
  void *Src; // [rsp+38h] [rbp-28h] BYREF
  PVOID P; // [rsp+40h] [rbp-20h] BYREF
  PVOID Object; // [rsp+48h] [rbp-18h] BYREF
  HANDLE FileHandle; // [rsp+50h] [rbp-10h] BYREF
  size_t Size; // [rsp+A8h] [rbp+48h] BYREF
  int v30; // [rsp+B8h] [rbp+58h]

  v30 = a4;
  PoolWithTag = 0;
  v8 = a1 + 64;
  v23 = 0;
  LODWORD(Size) = 0;
  FileHandle = 0;
  Object = 0;
  Src = 0;
  P = 0;
  v10 = WimPathToBootEnvironmentDevice((int)a1 + 64, a2 + 64, a3, (unsigned int)&P, (__int64)&Size);
  if ( v10 < 0 )
    goto LABEL_28;
  v11 = WimReadOverlayConfig(a1, 1, &FileHandle, (PFILE_OBJECT *)&Object, &Src, (__int64)&v23);
  v12 = Src;
  v10 = v11;
  if ( v11 >= 0 )
  {
    v13 = *((unsigned int *)Src + 2);
    v14 = v23 + v13 + Size;
    if ( v14 > 0x200000 || *((_DWORD *)Src + 3) >= 0x100u )
    {
      v10 = -1073740761;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, 3221226535LL);
    }
    else
    {
      PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, v14, 0x66637077u);
      if ( PoolWithTag )
      {
        LODWORD(Src) = v12[3] * v13 + 24;
        memmove(PoolWithTag, v12, (unsigned int)Src);
        v15 = &PoolWithTag[*((_DWORD *)PoolWithTag + 2) * *((_DWORD *)PoolWithTag + 3)];
        memset(v15 + 24, 0, v13);
        v16 = *((_QWORD *)PoolWithTag + 2);
        v17 = 0;
        v18 = v23;
        *((_DWORD *)v15 + 10) = v30;
        *((_DWORD *)v15 + 11) = a5;
        *((_DWORD *)v15 + 9) = Size;
        v19 = a6;
        *((_QWORD *)v15 + 3) = v16;
        *((_DWORD *)v15 + 8) = v18;
        *((_OWORD *)v15 + 3) = *v19;
        ++*((_DWORD *)PoolWithTag + 3);
        ++*((_QWORD *)PoolWithTag + 2);
        if ( *((_DWORD *)PoolWithTag + 3) )
        {
          do
          {
            v20 = v17++;
            *(_DWORD *)&PoolWithTag[*((_DWORD *)PoolWithTag + 2) * v20 + 32] += v13;
          }
          while ( v17 < *((_DWORD *)PoolWithTag + 3) );
        }
        memmove(
          &PoolWithTag[(unsigned int)(v13 + (_DWORD)Src)],
          (char *)v12 + (unsigned int)Src,
          (unsigned int)(v18 - (_DWORD)Src));
        memmove(&PoolWithTag[(unsigned int)(v13 + v23)], P, (unsigned int)Size);
        v21 = WimWriteOverlayConfig(a1, FileHandle, (struct _FILE_OBJECT *)Object, PoolWithTag, v14);
        v10 = v21;
        if ( v21 >= 0 )
        {
          WimPublishConfigChangeNotification();
          *a7 = v16;
        }
        else if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Zd(
            WPP_GLOBAL_Control->AttachedDevice,
            48,
            (unsigned int)WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids,
            v8,
            v21);
        }
        goto LABEL_24;
      }
      v10 = -1073741801;
    }
  }
  else if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Zd(
      WPP_GLOBAL_Control->AttachedDevice,
      46,
      (unsigned int)WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids,
      v8,
      v11);
  }
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose(FileHandle);
LABEL_24:
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
LABEL_28:
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14002ad28  mov     r11, rsp
0x14002ad2b  mov     [r11+18h], rbx
0x14002ad2f  mov     [r11+20h], r9d
0x14002ad33  mov     [r11+8], rcx
0x14002ad37  push    rbp
0x14002ad38  push    rsi
0x14002ad39  push    rdi
0x14002ad3a  push    r12
0x14002ad3c  push    r13
0x14002ad3e  push    r14
0x14002ad40  push    r15
0x14002ad42  mov     rbp, rsp
0x14002ad45  sub     rsp, 60h
0x14002ad49  xor     esi, esi
0x14002ad4b  lea     r13, [rcx+40h]
0x14002ad4f  mov     rbx, rcx
0x14002ad52  mov     [rbp+var_30], esi
0x14002ad55  lea     rax, [rbp+Size]
0x14002ad59  mov     dword ptr [rbp+Size], esi
0x14002ad5c  mov     rcx, r13
0x14002ad5f  mov     [rbp+FileHandle], rsi
0x14002ad63  add     rdx, 40h ; '@'
0x14002ad67  mov     [rbp+Object], rsi
0x14002ad6b  lea     r9, [rbp+P]
0x14002ad6f  mov     [rbp+Src], rsi
0x14002ad73  mov     [rbp+P], rsi
0x14002ad77  mov     [r11-78h], rax
0x14002ad7b  call    WimPathToBootEnvironmentDevice
0x14002ad80  mov     edi, eax
0x14002ad82  test    eax, eax
0x14002ad84  js      loc_14002AFEC
0x14002ad8a  lea     rax, [rbp+var_30]
0x14002ad8e  mov     dl, 1
0x14002ad90  mov     [rsp+60h+var_38], rax
0x14002ad95  lea     r9, [rbp+Object]
0x14002ad99  lea     rax, [rbp+Src]
0x14002ad9d  mov     rcx, rbx
0x14002ada0  lea     r8, [rbp+FileHandle]
0x14002ada4  mov     [rsp+60h+var_40], rax
0x14002ada9  call    WimReadOverlayConfig
0x14002adae  mov     r14, [rbp+Src]
0x14002adb2  mov     edi, eax
0x14002adb4  test    eax, eax
0x14002adb6  jns     short loc_14002ADF5
0x14002adb8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002adbf  test    dword ptr [rcx+2Ch], 400h
0x14002adc6  jz      loc_14002AF94
0x14002adcc  cmp     byte ptr [rcx+29h], 2
0x14002add0  jb      loc_14002AF94
0x14002add6  mov     rcx, [rcx+18h]
0x14002adda  lea     edx, [rsi+2Eh]
0x14002addd  mov     r9, r13
0x14002ade0  mov     dword ptr [rsp+60h+var_40], eax
0x14002ade4  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002adeb  call    WPP_SF_Zd
0x14002adf0  jmp     loc_14002AF94
0x14002adf5  mov     r15d, [r14+8]
0x14002adf9  mov     r12d, dword ptr [rbp+Size]
0x14002adfd  add     r12d, r15d
0x14002ae00  add     r12d, [rbp+var_30]
0x14002ae04  cmp     r12d, 200000h
0x14002ae0b  ja      loc_14002AF61
0x14002ae11  cmp     dword ptr [r14+0Ch], 100h
0x14002ae19  jnb     loc_14002AF61
0x14002ae1f  mov     edx, r12d; NumberOfBytes
0x14002ae22  mov     ecx, 1; PoolType
0x14002ae27  mov     r8d, 66637077h; Tag
0x14002ae2d  call    cs:__imp_ExAllocatePoolWithTag
0x14002ae34  nop     dword ptr [rax+rax+00h]
0x14002ae39  mov     rsi, rax
0x14002ae3c  test    rax, rax
0x14002ae3f  jnz     short loc_14002AE4B
0x14002ae41  mov     edi, 0C0000017h
0x14002ae46  jmp     loc_14002AF94
0x14002ae4b  mov     eax, r15d
0x14002ae4e  mov     rdx, r14; Src
0x14002ae51  imul    eax, [r14+0Ch]
0x14002ae56  mov     rcx, rsi; void *
0x14002ae59  add     eax, 18h
0x14002ae5c  mov     r8d, eax; Size
0x14002ae5f  mov     dword ptr [rbp+Src], eax
0x14002ae62  call    memmove
0x14002ae67  mov     edi, [rsi+0Ch]
0x14002ae6a  mov     r8, r15; Size
0x14002ae6d  imul    edi, [rsi+8]
0x14002ae71  xor     edx, edx; Val
0x14002ae73  add     rdi, rsi
0x14002ae76  lea     rcx, [rdi+18h]; void *
0x14002ae7a  call    memset
0x14002ae7f  mov     rbx, [rsi+10h]
0x14002ae83  xor     edx, edx
0x14002ae85  mov     eax, [rbp+arg_18]
0x14002ae88  mov     r8d, [rbp+var_30]
0x14002ae8c  mov     [rdi+28h], eax
0x14002ae8f  mov     eax, [rbp+arg_20]
0x14002ae92  mov     [rdi+2Ch], eax
0x14002ae95  mov     eax, dword ptr [rbp+Size]
0x14002ae98  mov     [rdi+24h], eax
0x14002ae9b  mov     rax, [rbp+arg_28]
0x14002ae9f  mov     [rdi+18h], rbx
0x14002aea3  mov     [rdi+20h], r8d
0x14002aea7  movups  xmm0, xmmword ptr [rax]
0x14002aeaa  movdqu  xmmword ptr [rdi+30h], xmm0
0x14002aeaf  inc     dword ptr [rsi+0Ch]
0x14002aeb2  inc     qword ptr [rsi+10h]
0x14002aeb6  cmp     [rsi+0Ch], edx
0x14002aeb9  jz      short loc_14002AECD
0x14002aebb  mov     eax, edx
0x14002aebd  inc     edx
0x14002aebf  imul    eax, [rsi+8]
0x14002aec3  add     [rax+rsi+20h], r15d
0x14002aec8  cmp     edx, [rsi+0Ch]
0x14002aecb  jb      short loc_14002AEBB
0x14002aecd  mov     ecx, dword ptr [rbp+Src]
0x14002aed0  sub     r8d, ecx; Size
0x14002aed3  lea     rdx, [r14+rcx]; Src
0x14002aed7  add     ecx, r15d
0x14002aeda  add     rcx, rsi; void *
0x14002aedd  call    memmove
0x14002aee2  mov     ecx, [rbp+var_30]
0x14002aee5  mov     r8d, dword ptr [rbp+Size]; Size
0x14002aee9  add     ecx, r15d
0x14002aeec  mov     rdx, [rbp+P]; Src
0x14002aef0  add     rcx, rsi; void *
0x14002aef3  call    memmove
0x14002aef8  mov     r8, [rbp+Object]
0x14002aefc  mov     r9, rsi
0x14002aeff  mov     rdx, [rbp+FileHandle]
0x14002af03  mov     rcx, [rbp+arg_0]
0x14002af07  mov     dword ptr [rsp+60h+var_40], r12d
0x14002af0c  call    WimWriteOverlayConfig
0x14002af11  mov     edi, eax
0x14002af13  test    eax, eax
0x14002af15  jns     short loc_14002AF53
0x14002af17  mov     rcx, cs:WPP_GLOBAL_Control
0x14002af1e  test    dword ptr [rcx+2Ch], 400h
0x14002af25  jz      loc_14002AFBE
0x14002af2b  cmp     byte ptr [rcx+29h], 2
0x14002af2f  jb      loc_14002AFBE
0x14002af35  mov     rcx, [rcx+18h]
0x14002af39  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002af40  mov     edx, 30h ; '0'
0x14002af45  mov     dword ptr [rsp+60h+var_40], eax
0x14002af49  mov     r9, r13
0x14002af4c  call    WPP_SF_Zd
0x14002af51  jmp     short loc_14002AFBE
0x14002af53  call    WimPublishConfigChangeNotification
0x14002af58  mov     rax, [rbp+arg_30]
0x14002af5c  mov     [rax], rbx
0x14002af5f  jmp     short loc_14002AFBE
0x14002af61  mov     edi, 0C0000427h
0x14002af66  mov     rcx, cs:WPP_GLOBAL_Control
0x14002af6d  test    dword ptr [rcx+2Ch], 400h
0x14002af74  jz      short loc_14002AF94
0x14002af76  cmp     byte ptr [rcx+29h], 2
0x14002af7a  jb      short loc_14002AF94
0x14002af7c  mov     rcx, [rcx+18h]
0x14002af80  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002af87  mov     edx, 2Fh ; '/'
0x14002af8c  mov     r9d, edi
0x14002af8f  call    WPP_SF_d
0x14002af94  mov     rcx, [rbp+Object]; Object
0x14002af98  test    rcx, rcx
0x14002af9b  jz      short loc_14002AFA9
0x14002af9d  call    cs:__imp_ObfDereferenceObject
0x14002afa4  nop     dword ptr [rax+rax+00h]
0x14002afa9  mov     rcx, [rbp+FileHandle]; FileHandle
0x14002afad  test    rcx, rcx
0x14002afb0  jz      short loc_14002AFBE
0x14002afb2  call    cs:__imp_FltClose
0x14002afb9  nop     dword ptr [rax+rax+00h]
0x14002afbe  test    r14, r14
0x14002afc1  jz      short loc_14002AFD4
0x14002afc3  xor     edx, edx; Tag
0x14002afc5  mov     rcx, r14; P
0x14002afc8  call    cs:__imp_ExFreePoolWithTag
0x14002afcf  nop     dword ptr [rax+rax+00h]
0x14002afd4  test    rsi, rsi
0x14002afd7  jz      short loc_14002AFEA
0x14002afd9  xor     edx, edx; Tag
0x14002afdb  mov     rcx, rsi; P
0x14002afde  call    cs:__imp_ExFreePoolWithTag
0x14002afe5  nop     dword ptr [rax+rax+00h]
0x14002afea  xor     esi, esi
0x14002afec  cmp     [rbp+P], rsi
0x14002aff0  jz      short loc_14002B004
0x14002aff2  mov     rcx, [rbp+P]; P
0x14002aff6  xor     edx, edx; Tag
0x14002aff8  call    cs:__imp_ExFreePoolWithTag
0x14002afff  nop     dword ptr [rax+rax+00h]
0x14002b004  mov     rbx, [rsp+60h+arg_10]
0x14002b00c  mov     eax, edi
0x14002b00e  add     rsp, 60h
0x14002b012  pop     r15
0x14002b014  pop     r14
0x14002b016  pop     r13
0x14002b018  pop     r12
0x14002b01a  pop     rdi
0x14002b01b  pop     rsi
0x14002b01c  pop     rbp
0x14002b01d  retn
```
