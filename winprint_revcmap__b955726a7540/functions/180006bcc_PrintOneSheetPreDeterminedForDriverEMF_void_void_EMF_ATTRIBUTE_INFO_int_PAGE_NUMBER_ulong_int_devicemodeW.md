# PrintOneSheetPreDeterminedForDriverEMF(void *,void *,_EMF_ATTRIBUTE_INFO *,int,_PAGE_NUMBER *,ulong,int *,_devicemodeW *)

- ea: `0x180006bcc`
- end: `0x180006e09`
- name: `?PrintOneSheetPreDeterminedForDriverEMF@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@HPEAU_PAGE_NUMBER@@KPEAHPEAU_devicemodeW@@@Z`
- size: `573`
- prototype: `__int64 __usercall@<rax>(HANDLE SpoolFileHandle@<rcx>, void *@<rdx>, struct _EMF_ATTRIBUTE_INFO *@<r8>, int@<r9d>, struct _PAGE_NUMBER *, unsigned int, int *, struct _devicemodeW *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800070e0`
- `0x180007540`

## callees

- `0x180001d60`
- `0x180003200`
- `0x180006324`
- `0x180006bcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c84`
- `GDI32!GdiGetPageHandle` at `0x180006c76`
- `GDI32!GdiGetPageHandle` at `0x180006c76`
- `GDI32!GdiStartPageEMF` at `0x180006d20`
- `GDI32!GdiStartPageEMF` at `0x180006d20`
- `GDI32!GdiEndPageEMF` at `0x180006d5e`
- `GDI32!GdiEndPageEMF` at `0x180006d5e`

## pseudocode

```c
__int64 __fastcall PrintOneSheetPreDeterminedForDriverEMF(
        HANDLE SpoolFileHandle,
        HDC a2,
        struct _EMF_ATTRIBUTE_INFO *a3,
        int a4,
        struct _PAGE_NUMBER *a5,
        DWORD dwOptimization,
        int *a7,
        struct _devicemodeW *a8)
{
  unsigned int v8; // edx
  unsigned int v11; // ebx
  int v12; // esi
  unsigned int v13; // edi
  struct _PAGE_NUMBER *i; // rbp
  DWORD v15; // r14d
  HANDLE PageHandle; // r13
  BOOL v17; // eax
  DWORD pdwPageType; // [rsp+50h] [rbp-58h] BYREF
  int pCurrDM; // [rsp+54h] [rbp-54h] BYREF
  int v21; // [rsp+58h] [rbp-50h]
  int v22; // [rsp+5Ch] [rbp-4Ch]
  unsigned int v23; // [rsp+60h] [rbp-48h]
  unsigned int v24; // [rsp+64h] [rbp-44h]
  struct _devicemodeW *v25; // [rsp+68h] [rbp-40h] BYREF
  int v28; // [rsp+C8h] [rbp+20h]

  v8 = *((_DWORD *)a3 + 9);
  v11 = 1;
  pdwPageType = 0;
  v24 = v8;
  pCurrDM = 0;
  v12 = (a4 != 0) + 1;
  v28 = 0;
  v13 = 0;
  v22 = v8 * v12;
  v23 = *((_DWORD *)a3 + 7);
  v21 = *((_DWORD *)a3 + 18);
  while ( 2 )
  {
    if ( v12 && a5 )
    {
      for ( i = a5; i; i = (struct _PAGE_NUMBER *)*((_QWORD *)i + 1) )
      {
        v15 = *((_DWORD *)i + 4);
        if ( !v15 )
          v15 = -1;
        PageHandle = GdiGetPageHandle(SpoolFileHandle, v15, &pdwPageType);
        if ( PageHandle )
        {
          if ( v13 )
          {
            if ( !(unsigned int)BPlayEmptyPages(SpoolFileHandle, v13, dwOptimization) )
              return 0;
            v13 = 0;
          }
          if ( !(unsigned int)ResetDCForNewDevmode(
                                SpoolFileHandle,
                                a2,
                                a3,
                                v15,
                                0,
                                dwOptimization,
                                (PDEVMODEW)&pCurrDM,
                                a8,
                                &v25)
            || !GdiStartPageEMF(SpoolFileHandle)
            || !(unsigned int)PlayEMFPage(SpoolFileHandle, a2, PageHandle, a3, 1u, 1)
            || !GdiEndPageEMF(SpoolFileHandle, dwOptimization) )
          {
            return 0;
          }
        }
        else
        {
          if ( GetLastError() != 259 )
            return 0;
          ++v13;
          v28 = 1;
        }
      }
      if ( v13 )
      {
        v17 = a8->dmSize >= 0x66u && a8->dmCollate != 1;
        if ( v21 )
        {
          if ( v17 && v23 <= v24 )
            goto LABEL_31;
        }
        else if ( v12 != 1 || v22 == v13 )
        {
          goto LABEL_31;
        }
        BPlayEmptyPages(SpoolFileHandle, v13, dwOptimization);
        v13 = 0;
      }
LABEL_31:
      a5 = *(struct _PAGE_NUMBER **)a5;
      --v12;
      continue;
    }
    break;
  }
  if ( a7 )
    *a7 = v28;
  return v11;
}

```

## disassembly

```asm
0x180006bcc  mov     rax, rsp
0x180006bcf  mov     [rax+8], rbx
0x180006bd3  mov     [rax+18h], r8
0x180006bd7  mov     [rax+10h], rdx
0x180006bdb  push    rbp
0x180006bdc  push    rsi
0x180006bdd  push    rdi
0x180006bde  push    r12
0x180006be0  push    r13
0x180006be2  push    r14
0x180006be4  push    r15
0x180006be6  sub     rsp, 70h
0x180006bea  mov     edx, [r8+24h]
0x180006bee  mov     r15, rcx
0x180006bf1  mov     r12, [rsp+0A8h+arg_20]
0x180006bf9  neg     r9d
0x180006bfc  mov     ebx, 1
0x180006c01  mov     dword ptr [rax-58h], 0
0x180006c08  sbb     esi, esi
0x180006c0a  mov     [rsp+0A8h+var_44], edx
0x180006c0e  neg     esi
0x180006c10  mov     dword ptr [rax-54h], 0
0x180006c17  add     esi, ebx
0x180006c19  mov     [rsp+0A8h+arg_18], 0
0x180006c24  mov     ecx, esi
0x180006c26  xor     edi, edi
0x180006c28  imul    ecx, edx
0x180006c2b  or      r13d, 0FFFFFFFFh
0x180006c2f  mov     [rsp+0A8h+var_4C], ecx
0x180006c33  mov     ecx, [r8+1Ch]
0x180006c37  mov     [rsp+0A8h+var_48], ecx
0x180006c3b  mov     ecx, [r8+48h]
0x180006c3f  mov     [rsp+0A8h+var_50], ecx
0x180006c43  test    esi, esi
0x180006c45  jz      loc_180006DD9
0x180006c4b  test    r12, r12
0x180006c4e  jz      loc_180006DD9
0x180006c54  mov     rbp, r12
0x180006c57  test    rbp, rbp
0x180006c5a  jz      loc_180006D75
0x180006c60  mov     r14d, [rbp+10h]
0x180006c64  lea     r8, [rsp+0A8h+pdwPageType]; pdwPageType
0x180006c69  test    r14d, r14d
0x180006c6c  mov     rcx, r15; SpoolFileHandle
0x180006c6f  cmovz   r14d, r13d
0x180006c73  mov     edx, r14d; Page
0x180006c76  call    cs:__imp_GdiGetPageHandle
0x180006c7c  mov     r13, rax
0x180006c7f  test    rax, rax
0x180006c82  jnz     short loc_180006CA3
0x180006c84  call    cs:__imp_GetLastError
0x180006c8a  cmp     eax, 103h
0x180006c8f  jnz     loc_180006DD5
0x180006c95  add     edi, ebx
0x180006c97  mov     [rsp+0A8h+arg_18], ebx
0x180006c9e  jmp     loc_180006D68
0x180006ca3  test    edi, edi
0x180006ca5  jz      short loc_180006CC3
0x180006ca7  mov     r8d, [rsp+0A8h+dwOptimization]; unsigned int
0x180006caf  mov     edx, edi; unsigned int
0x180006cb1  mov     rcx, r15; SpoolFileHandle
0x180006cb4  call    ?BPlayEmptyPages@@YAHPEAXKK@Z; BPlayEmptyPages(void *,ulong,ulong)
0x180006cb9  test    eax, eax
0x180006cbb  jz      loc_180006DD5
0x180006cc1  xor     edi, edi
0x180006cc3  mov     rdx, [rsp+0A8h+hdc]; hdc
0x180006ccb  lea     rax, [rsp+0A8h+var_40]
0x180006cd0  mov     [rsp+0A8h+var_68], rax; struct _devicemodeW **
0x180006cd5  mov     r9d, r14d; dwPageNumber
0x180006cd8  mov     rax, [rsp+0A8h+arg_38]
0x180006ce0  mov     rcx, r15; SpoolFileHandle
0x180006ce3  mov     r14, [rsp+0A8h+arg_10]
0x180006ceb  mov     [rsp+0A8h+var_70], rax; struct _devicemodeW *
0x180006cf0  mov     r8, r14; struct _EMF_ATTRIBUTE_INFO *
0x180006cf3  lea     rax, [rsp+0A8h+var_54]
0x180006cf8  mov     [rsp+0A8h+pCurrDM], rax; pCurrDM
0x180006cfd  mov     eax, [rsp+0A8h+dwOptimization]
0x180006d04  mov     [rsp+0A8h+var_80], eax; dwOptimization
0x180006d08  mov     [rsp+0A8h+var_88], 0; int
0x180006d10  call    ?ResetDCForNewDevmode@@YAHPEAX0PEAU_EMF_ATTRIBUTE_INFO@@KHKPEAHPEAU_devicemodeW@@PEAPEAU2@@Z; ResetDCForNewDevmode(void *,void *,_EMF_ATTRIBUTE_INFO *,ulong,int,ulong,int *,_devicemodeW *,_devicemodeW * *)
0x180006d15  test    eax, eax
0x180006d17  jz      loc_180006DD5
0x180006d1d  mov     rcx, r15; SpoolFileHandle
0x180006d20  call    cs:__imp_GdiStartPageEMF
0x180006d26  test    eax, eax
0x180006d28  jz      loc_180006DD5
0x180006d2e  mov     rdx, [rsp+0A8h+hdc]; hdc
0x180006d36  mov     r9, r14; struct _EMF_ATTRIBUTE_INFO *
0x180006d39  mov     [rsp+0A8h+var_80], ebx; unsigned int
0x180006d3d  mov     r8, r13; void *
0x180006d40  mov     rcx, r15; SpoolFileHandle
0x180006d43  mov     [rsp+0A8h+var_88], ebx; unsigned int
0x180006d47  call    ?PlayEMFPage@@YAHPEAX00QEAU_EMF_ATTRIBUTE_INFO@@KK@Z; PlayEMFPage(void *,void *,void *,_EMF_ATTRIBUTE_INFO * const,ulong,ulong)
0x180006d4c  test    eax, eax
0x180006d4e  jz      loc_180006DD5
0x180006d54  mov     edx, [rsp+0A8h+dwOptimization]; dwOptimization
0x180006d5b  mov     rcx, r15; SpoolFileHandle
0x180006d5e  call    cs:__imp_GdiEndPageEMF
0x180006d64  test    eax, eax
0x180006d66  jz      short loc_180006DD5
0x180006d68  mov     rbp, [rbp+8]
0x180006d6c  or      r13d, 0FFFFFFFFh
0x180006d70  jmp     loc_180006C57
0x180006d75  test    edi, edi
0x180006d77  jz      short loc_180006DC9
0x180006d79  mov     rax, [rsp+0A8h+arg_38]
0x180006d81  cmp     word ptr [rax+44h], 66h ; 'f'
0x180006d86  jb      short loc_180006D92
0x180006d88  cmp     [rax+64h], bx
0x180006d8c  jz      short loc_180006D92
0x180006d8e  mov     eax, ebx
0x180006d90  jmp     short loc_180006D94
0x180006d92  xor     eax, eax
0x180006d94  cmp     [rsp+0A8h+var_50], 0
0x180006d99  jnz     short loc_180006DA7
0x180006d9b  cmp     esi, ebx
0x180006d9d  jnz     short loc_180006DC9
0x180006d9f  cmp     [rsp+0A8h+var_4C], edi
0x180006da3  jz      short loc_180006DC9
0x180006da5  jmp     short loc_180006DB5
0x180006da7  test    eax, eax
0x180006da9  jz      short loc_180006DB5
0x180006dab  mov     eax, [rsp+0A8h+var_48]
0x180006daf  cmp     eax, [rsp+0A8h+var_44]
0x180006db3  jbe     short loc_180006DC9
0x180006db5  mov     r8d, [rsp+0A8h+dwOptimization]; unsigned int
0x180006dbd  mov     edx, edi; unsigned int
0x180006dbf  mov     rcx, r15; SpoolFileHandle
0x180006dc2  call    ?BPlayEmptyPages@@YAHPEAXKK@Z; BPlayEmptyPages(void *,ulong,ulong)
0x180006dc7  xor     edi, edi
0x180006dc9  mov     r12, [r12]
0x180006dcd  add     esi, r13d
0x180006dd0  jmp     loc_180006C43
0x180006dd5  xor     ebx, ebx
0x180006dd7  jmp     short loc_180006DEF
0x180006dd9  mov     rax, [rsp+0A8h+arg_30]
0x180006de1  test    rax, rax
0x180006de4  jz      short loc_180006DEF
0x180006de6  mov     ecx, [rsp+0A8h+arg_18]
0x180006ded  mov     [rax], ecx
0x180006def  mov     eax, ebx
0x180006df1  mov     rbx, [rsp+0A8h+arg_0]
0x180006df9  add     rsp, 70h
0x180006dfd  pop     r15
0x180006dff  pop     r14
0x180006e01  pop     r13
0x180006e03  pop     r12
0x180006e05  pop     rdi
0x180006e06  pop     rsi
0x180006e07  pop     rbp
0x180006e08  retn
```
