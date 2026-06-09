# ResetDCForNewDevmode(void *,void *,_EMF_ATTRIBUTE_INFO *,ulong,int,ulong,int *,_devicemodeW *,_devicemodeW * *)

- ea: `0x180003200`
- end: `0x180003387`
- name: `?ResetDCForNewDevmode@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@KHKPEAHPEAU_devicemodeW@@PEAPEAU2@@Z`
- size: `391`
- prototype: `__int64 __fastcall(HANDLE SpoolFileHandle, HDC hdc, struct _EMF_ATTRIBUTE_INFO *, DWORD dwPageNumber, int, DWORD dwOptimization, PDEVMODEW pCurrDM, struct _devicemodeW *, struct _devicemodeW **)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180006bcc`
- `0x180006e10`
- `0x180007210`

## callees

- `0x180003200`
- `0x180003cf0`
- `0x1800044a0`
- `0x180006370`

## import_xrefs

- `GDI32!GdiGetDevmodeForPage` at `0x18000323b`
- `GDI32!GdiGetDevmodeForPage` at `0x18000323b`
- `GDI32!SetGraphicsMode` at `0x180003360`
- `GDI32!SetGraphicsMode` at `0x180003360`
- `GDI32!GdiResetDCEMF` at `0x180003352`
- `GDI32!GdiResetDCEMF` at `0x180003352`
- `GDI32!GdiEndPageEMF` at `0x1800032d1`
- `GDI32!GdiEndPageEMF` at `0x1800032d1`

## pseudocode

```c
__int64 __fastcall ResetDCForNewDevmode(
        HANDLE SpoolFileHandle,
        HDC hdc,
        struct _EMF_ATTRIBUTE_INFO *a3,
        DWORD dwPageNumber,
        int a5,
        DWORD dwOptimization,
        PDEVMODEW pCurrDM,
        struct _devicemodeW *a8,
        struct _devicemodeW **a9)
{
  PDEVMODEW v9; // rbx
  PDEVMODEW v13; // r14
  struct _devicemodeW *v14; // rcx
  struct _devicemodeW *v15; // rdx
  struct _devicemodeW *v17; // [rsp+20h] [rbp-48h] BYREF

  v9 = pCurrDM;
  pCurrDM = 0;
  v17 = 0;
  *(_DWORD *)v9->dmDeviceName = 0;
  if ( GdiGetDevmodeForPage(SpoolFileHandle, dwPageNumber, &pCurrDM, &v17) )
  {
    v13 = pCurrDM;
    if ( pCurrDM )
    {
      if ( (unsigned int)BIsDevmodeOfLeastAcceptableSize(pCurrDM) )
      {
        v14 = v17;
        if ( !v17 || (unsigned int)BIsDevmodeOfLeastAcceptableSize(v17) )
        {
          if ( a9 )
            *a9 = v13;
          if ( v14 == v13 || a5 && !(unsigned int)DifferentDevmodes(v14, v13) )
          {
            if ( !*(_DWORD *)v9->dmDeviceName )
              return 1;
          }
          else
          {
            *(_DWORD *)v9->dmDeviceName = 1;
          }
          if ( !a5 )
          {
LABEL_16:
            if ( v13 )
            {
              v15 = a8;
              v13->dmPrintQuality = a8->dmPrintQuality;
              pCurrDM->dmYResolution = v15->dmYResolution;
              pCurrDM->dmCopies = v15->dmCopies;
              v13 = pCurrDM;
              if ( pCurrDM->dmSize >= 0x66u )
              {
                if ( v15->dmSize < 0x66u )
                  pCurrDM->dmCollate = 0;
                else
                  pCurrDM->dmCollate = v15->dmCollate;
                v13 = pCurrDM;
              }
            }
            GdiResetDCEMF(SpoolFileHandle, v13);
            SetGraphicsMode(hdc, 2);
            BUpdateAttributes(hdc, a3);
            return 1;
          }
          if ( GdiEndPageEMF(SpoolFileHandle, dwOptimization) )
          {
            v13 = pCurrDM;
            goto LABEL_16;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003200  mov     r11, rsp
0x180003203  push    rbx
0x180003204  push    rbp
0x180003205  push    rsi
0x180003206  push    rdi
0x180003207  push    r12
0x180003209  push    r14
0x18000320b  sub     rsp, 38h
0x18000320f  mov     rbx, [rsp+68h+pCurrDM]
0x180003217  mov     eax, r9d
0x18000321a  xor     r12d, r12d
0x18000321d  lea     r9, [r11-48h]; pLastDM
0x180003221  mov     rbp, r8
0x180003224  mov     [r11+38h], r12
0x180003228  mov     rsi, rdx
0x18000322b  mov     [r11-48h], r12
0x18000322f  lea     r8, [r11+38h]; pCurrDM
0x180003233  mov     [rbx], r12d
0x180003236  mov     edx, eax; dwPageNumber
0x180003238  mov     rdi, rcx
0x18000323b  call    cs:__imp_GdiGetDevmodeForPage
0x180003241  test    eax, eax
0x180003243  jz      loc_180003378
0x180003249  mov     r14, [rsp+68h+pCurrDM]
0x180003251  test    r14, r14
0x180003254  jz      loc_180003378
0x18000325a  mov     rcx, r14; struct _devicemodeW *
0x18000325d  call    ?BIsDevmodeOfLeastAcceptableSize@@YAHPEAU_devicemodeW@@@Z; BIsDevmodeOfLeastAcceptableSize(_devicemodeW *)
0x180003262  test    eax, eax
0x180003264  jz      loc_180003378
0x18000326a  mov     rcx, [rsp+68h+var_48]; struct _devicemodeW *
0x18000326f  test    rcx, rcx
0x180003272  jz      short loc_180003281
0x180003274  call    ?BIsDevmodeOfLeastAcceptableSize@@YAHPEAU_devicemodeW@@@Z; BIsDevmodeOfLeastAcceptableSize(_devicemodeW *)
0x180003279  test    eax, eax
0x18000327b  jz      loc_180003378
0x180003281  mov     rax, [rsp+68h+arg_40]
0x180003289  test    rax, rax
0x18000328c  jz      short loc_180003291
0x18000328e  mov     [rax], r14
0x180003291  cmp     rcx, r14
0x180003294  jz      short loc_1800032B4
0x180003296  cmp     [rsp+68h+arg_20], r12d
0x18000329e  jz      short loc_1800032AC
0x1800032a0  mov     rdx, r14; struct _devicemodeW *
0x1800032a3  call    ?DifferentDevmodes@@YAHPEAU_devicemodeW@@0@Z; DifferentDevmodes(_devicemodeW *,_devicemodeW *)
0x1800032a8  test    eax, eax
0x1800032aa  jz      short loc_1800032B4
0x1800032ac  mov     dword ptr [rbx], 1
0x1800032b2  jmp     short loc_1800032BD
0x1800032b4  cmp     [rbx], r12d
0x1800032b7  jz      loc_180003371
0x1800032bd  cmp     [rsp+68h+arg_20], r12d
0x1800032c5  jz      short loc_1800032E7
0x1800032c7  mov     edx, [rsp+68h+dwOptimization]; dwOptimization
0x1800032ce  mov     rcx, rdi; SpoolFileHandle
0x1800032d1  call    cs:__imp_GdiEndPageEMF
0x1800032d7  test    eax, eax
0x1800032d9  jz      loc_180003378
0x1800032df  mov     r14, [rsp+68h+pCurrDM]
0x1800032e7  test    r14, r14
0x1800032ea  jz      short loc_18000334C
0x1800032ec  mov     rdx, [rsp+68h+arg_38]
0x1800032f4  movzx   eax, word ptr [rdx+5Ah]
0x1800032f8  mov     [r14+5Ah], ax
0x1800032fd  mov     rax, [rsp+68h+pCurrDM]
0x180003305  movzx   ecx, word ptr [rdx+60h]
0x180003309  mov     [rax+60h], cx
0x18000330d  mov     rax, [rsp+68h+pCurrDM]
0x180003315  movzx   ecx, word ptr [rdx+56h]
0x180003319  mov     [rax+56h], cx
0x18000331d  mov     r14, [rsp+68h+pCurrDM]
0x180003325  cmp     word ptr [r14+44h], 66h ; 'f'
0x18000332b  jb      short loc_18000334C
0x18000332d  cmp     word ptr [rdx+44h], 66h ; 'f'
0x180003332  jb      short loc_18000333F
0x180003334  movzx   eax, word ptr [rdx+64h]
0x180003338  mov     [r14+64h], ax
0x18000333d  jmp     short loc_180003344
0x18000333f  mov     [r14+64h], r12w
0x180003344  mov     r14, [rsp+68h+pCurrDM]
0x18000334c  mov     rdx, r14; pCurrDM
0x18000334f  mov     rcx, rdi; SpoolFileHandle
0x180003352  call    cs:__imp_GdiResetDCEMF
0x180003358  mov     edx, 2; iMode
0x18000335d  mov     rcx, rsi; hdc
0x180003360  call    cs:__imp_SetGraphicsMode
0x180003366  mov     rdx, rbp; struct _EMF_ATTRIBUTE_INFO *
0x180003369  mov     rcx, rsi; hdc
0x18000336c  call    ?BUpdateAttributes@@YAHPEAXPEAU_EMF_ATTRIBUTE_INFO@@@Z; BUpdateAttributes(void *,_EMF_ATTRIBUTE_INFO *)
0x180003371  mov     eax, 1
0x180003376  jmp     short loc_18000337A
0x180003378  xor     eax, eax
0x18000337a  add     rsp, 38h
0x18000337e  pop     r14
0x180003380  pop     r12
0x180003382  pop     rdi
0x180003383  pop     rsi
0x180003384  pop     rbp
0x180003385  pop     rbx
0x180003386  retn
```
