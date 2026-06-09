# CVolumeEntryMap::GetVolumeNameArray(ulong *,ushort * * *)

- ea: `0x18000b5f4`
- end: `0x18000b8ac`
- name: `?GetVolumeNameArray@CVolumeEntryMap@@QEAAJPEAKPEAPEAPEAG@Z`
- size: `696`
- prototype: `__int64 __fastcall(CVolumeEntryMap *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `4`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800092e0`
- `0x18000a920`
- `0x18000b8c0`
- `0x18000c070`

## callees

- `0x180003544`
- `0x1800037e4`
- `0x18000702c`
- `0x18000b5f4`
- `0x18000cc50`
- `0x18000dd40`
- `0x18000e308`
- `0x18000e48c`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x180034f10`
- `0x18003532c`
- `0x180035b00`

## import_xrefs

- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18000b6ec`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18000b6ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b83f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b83f`

## pseudocode

```c
__int64 __fastcall CVolumeEntryMap::GetVolumeNameArray(CVolumeEntryMap *this, unsigned int *a2, unsigned __int16 ***a3)
{
  __int64 v6; // rbx
  __int16 v7; // ax
  struct _RTL_AVL_TABLE *v8; // rcx
  ULONG v9; // eax
  CVolumeEntryMap *v10; // rax
  int v11; // ecx
  CVolumeEntry *v12; // rdi
  unsigned __int16 **v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // edi
  __int64 v16; // rdx
  __int64 v17; // r8
  LPVOID pv; // [rsp+20h] [rbp-49h] BYREF
  unsigned __int16 *v20[2]; // [rsp+28h] [rbp-41h] BYREF
  int v21; // [rsp+38h] [rbp-31h] BYREF
  CVolumeEntryMap *v22[2]; // [rsp+40h] [rbp-29h]
  int v23; // [rsp+50h] [rbp-19h] BYREF
  __int16 v24; // [rsp+54h] [rbp-15h]
  __int16 v25; // [rsp+56h] [rbp-13h]
  CVolumeEntry *v26; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v23, "CVolumeEntryMap::GetVolumeNameArray", 332, 1);
  v20[0] = (unsigned __int16 *)&FileName;
  v6 = 0;
  v27 = 0;
  v21 = 0;
  v7 = 340;
  v26 = 0;
  v20[1] = 0;
  pv = 0;
  *(_OWORD *)v22 = 0;
  if ( !a2 || (v24 = 340, v7 = 341, !a3) )
  {
    v23 = -2147024809;
    goto LABEL_6;
  }
  v23 = 0;
  v24 = 341;
  v23 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::CreateInstance(&v27);
  if ( v23 < 0 )
  {
    v6 = v27;
    v25 = 343;
    goto LABEL_27;
  }
  v8 = *(struct _RTL_AVL_TABLE **)this;
  v24 = 343;
  v9 = RtlNumberGenericTableElementsAvl(v8);
  v6 = v27;
  v23 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Alloc(
          v27,
          v9);
  v7 = 344;
  if ( v23 < 0 )
  {
LABEL_6:
    v25 = v7;
    goto LABEL_27;
  }
  v24 = 344;
  v10 = v22[0];
  if ( v22[0] )
  {
    CVolumeEntryMap::Release(v22[0]);
    v10 = 0;
    v22[0] = 0;
  }
  v21 = 0;
  v22[1] = 0;
  if ( v10 )
  {
    v23 = -2147418113;
    v7 = 347;
    goto LABEL_6;
  }
  v22[0] = this;
  _InterlockedIncrement((volatile signed __int32 *)this + 4);
  v21 = *((_DWORD *)v22[0] + 2);
  v22[1] = 0;
  v23 = 0;
  v24 = 347;
  v11 = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v21, &v26);
  v23 = v11;
  v7 = 350;
  if ( v11 < 0 )
    goto LABEL_6;
  v24 = 350;
  while ( v11 != 1 )
  {
    v12 = v26;
    v23 = CBsString::Set((CBsString *)v20, *((const unsigned __int16 **)v26 + 1));
    v7 = 353;
    if ( v23 < 0 )
      goto LABEL_6;
    v24 = 353;
    CBsString::Detach((CBsString *)v20, (unsigned __int16 **)&pv);
    v23 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Append(
            v6,
            &pv);
    if ( v23 < 0 )
    {
      v25 = 355;
      goto LABEL_27;
    }
    v24 = 355;
    if ( v12 )
    {
      v26 = 0;
      CVolumeEntry::Release(v12);
    }
    v23 = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v21, &v26);
    v11 = v23;
    if ( v23 < 0 )
    {
      v25 = 358;
      goto LABEL_27;
    }
    v24 = 358;
  }
  v13 = *(unsigned __int16 ***)(v6 + 8);
  v14 = *(_DWORD *)(v6 + 16);
  *(_QWORD *)(v6 + 8) = 0;
  *(_QWORD *)(v6 + 16) = 0;
  *a3 = v13;
  *a2 = v14;
LABEL_27:
  CoTaskMemFree(pv);
  v15 = v23;
  CBsString::_Release(v20);
  if ( v6 )
    CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Release((void *)v6);
  if ( v26 )
    CVolumeEntry::Release(v26);
  if ( v22[0] )
  {
    CVolumeEntryMap::Release(v22[0]);
    v22[0] = 0;
  }
  v21 = 0;
  v22[1] = 0;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v23, v16, v17);
  return v15;
}

```

## disassembly

```asm
0x18000b5f4  mov     [rsp-8+arg_0], rbx
0x18000b5f9  push    rbp
0x18000b5fa  push    rsi
0x18000b5fb  push    rdi
0x18000b5fc  push    r12
0x18000b5fe  push    r13
0x18000b600  push    r14
0x18000b602  push    r15
0x18000b604  lea     rbp, [rsp-27h]
0x18000b609  sub     rsp, 90h
0x18000b610  mov     rsi, r8
0x18000b613  mov     r14, rdx
0x18000b616  mov     rdi, rcx
0x18000b619  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b620  lea     rax, WPP_GLOBAL_Control
0x18000b627  cmp     rcx, rax
0x18000b62a  jz      short loc_18000B64A
0x18000b62c  test    dword ptr [rcx+1Ch], 20000000h
0x18000b633  jz      short loc_18000B64A
0x18000b635  mov     rcx, [rcx+10h]
0x18000b639  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18000b640  mov     edx, 0Ah
0x18000b645  call    WPP_SF_
0x18000b64a  mov     r9d, 1; unsigned __int16
0x18000b650  lea     rdx, aCvolumeentryma; "CVolumeEntryMap::GetVolumeNameArray"
0x18000b657  mov     r8d, 14Ch; unsigned __int16
0x18000b65d  lea     rcx, [rbp+57h+var_70]; this
0x18000b661  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000b666  xor     r15d, r15d
0x18000b669  lea     rax, FileName
0x18000b670  mov     [rbp+57h+var_98], rax
0x18000b674  mov     ebx, r15d
0x18000b677  mov     [rbp+57h+arg_18], rbx
0x18000b67b  xorps   xmm0, xmm0
0x18000b67e  mov     [rbp+57h+var_88], r15d
0x18000b682  mov     eax, 154h
0x18000b687  mov     [rbp+57h+arg_8], r15
0x18000b68b  mov     [rbp+57h+var_90], r15
0x18000b68f  mov     [rbp+57h+pv], r15
0x18000b693  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x18000b698  test    r14, r14
0x18000b69b  jnz     short loc_18000B6AD
0x18000b69d  mov     [rbp+57h+var_70], 80070057h
0x18000b6a4  mov     [rbp+57h+var_6A], ax
0x18000b6a8  jmp     loc_18000B83B
0x18000b6ad  mov     [rbp+57h+var_6C], ax
0x18000b6b1  mov     eax, 155h
0x18000b6b6  test    rsi, rsi
0x18000b6b9  jz      short loc_18000B69D
0x18000b6bb  lea     rcx, [rbp+57h+arg_18]
0x18000b6bf  mov     [rbp+57h+var_70], r15d
0x18000b6c3  mov     [rbp+57h+var_6C], ax
0x18000b6c7  call    ?CreateInstance@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@SAJPEAPEAV1@@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::CreateInstance(CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)> * *)
0x18000b6cc  mov     [rbp+57h+var_70], eax
0x18000b6cf  test    eax, eax
0x18000b6d1  mov     eax, 157h
0x18000b6d6  jns     short loc_18000B6E5
0x18000b6d8  mov     rbx, [rbp+57h+arg_18]
0x18000b6dc  mov     [rbp+57h+var_6A], ax
0x18000b6e0  jmp     loc_18000B83B
0x18000b6e5  mov     rcx, [rdi]; Table
0x18000b6e8  mov     [rbp+57h+var_6C], ax
0x18000b6ec  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x18000b6f2  mov     rbx, [rbp+57h+arg_18]
0x18000b6f6  mov     edx, eax
0x18000b6f8  mov     rcx, rbx
0x18000b6fb  call    ?Alloc@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@QEAAJK@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::Alloc(ulong)
0x18000b700  mov     [rbp+57h+var_70], eax
0x18000b703  test    eax, eax
0x18000b705  mov     eax, 158h
0x18000b70a  js      short loc_18000B6A4
0x18000b70c  mov     [rbp+57h+var_6C], ax
0x18000b710  mov     rax, [rbp+57h+var_80]
0x18000b714  test    rax, rax
0x18000b717  jz      short loc_18000B728
0x18000b719  mov     rcx, rax; this
0x18000b71c  call    ?Release@CVolumeEntryMap@@QEAAKXZ; CVolumeEntryMap::Release(void)
0x18000b721  mov     rax, r15
0x18000b724  mov     [rbp+57h+var_80], rax
0x18000b728  mov     [rbp+57h+var_88], r15d
0x18000b72c  mov     [rbp+57h+var_80+8], r15
0x18000b730  test    rax, rax
0x18000b733  jz      short loc_18000B746
0x18000b735  mov     [rbp+57h+var_70], 8000FFFFh
0x18000b73c  mov     eax, 15Bh
0x18000b741  jmp     loc_18000B6A4
0x18000b746  mov     [rbp+57h+var_80], rdi
0x18000b74a  lock inc dword ptr [rdi+10h]
0x18000b74e  mov     rax, [rbp+57h+var_80]
0x18000b752  mov     ecx, [rax+8]
0x18000b755  mov     [rbp+57h+var_88], ecx
0x18000b758  mov     [rbp+57h+var_80+8], r15
0x18000b75c  mov     eax, 15Bh
0x18000b761  mov     [rbp+57h+var_70], r15d
0x18000b765  lea     rdx, [rbp+57h+arg_8]
0x18000b769  mov     [rbp+57h+var_6C], ax
0x18000b76d  lea     rcx, [rbp+57h+var_88]
0x18000b771  call    ?Next@CSxIter@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@QEAAJPEAPEAVCSxStringEntry@@@Z; CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(CSxStringEntry * *)
0x18000b776  mov     ecx, eax
0x18000b778  mov     [rbp+57h+var_70], eax
0x18000b77b  test    eax, eax
0x18000b77d  mov     eax, 15Eh
0x18000b782  js      loc_18000B6A4
0x18000b788  mov     [rbp+57h+var_6C], ax
0x18000b78c  lea     r13d, [rax+5]
0x18000b790  lea     r12d, [rax+8]
0x18000b794  cmp     ecx, 1
0x18000b797  jz      loc_18000B826
0x18000b79d  mov     rdi, [rbp+57h+arg_8]
0x18000b7a1  lea     rcx, [rbp+57h+var_98]; this
0x18000b7a5  mov     rdx, [rdi+8]; unsigned __int16 *
0x18000b7a9  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18000b7ae  mov     [rbp+57h+var_70], eax
0x18000b7b1  test    eax, eax
0x18000b7b3  mov     eax, 161h
0x18000b7b8  js      loc_18000B6A4
0x18000b7be  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x18000b7c2  mov     [rbp+57h+var_6C], ax
0x18000b7c6  lea     rcx, [rbp+57h+var_98]; this
0x18000b7ca  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x18000b7cf  lea     rdx, [rbp+57h+pv]
0x18000b7d3  mov     rcx, rbx
0x18000b7d6  call    ?Append@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@QEAAJPEAPEAG@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::Append(ushort * *)
0x18000b7db  mov     [rbp+57h+var_70], eax
0x18000b7de  test    eax, eax
0x18000b7e0  js      short loc_18000B81F
0x18000b7e2  mov     [rbp+57h+var_6C], r13w
0x18000b7e7  test    rdi, rdi
0x18000b7ea  jz      short loc_18000B7F8
0x18000b7ec  mov     rcx, rdi; this
0x18000b7ef  mov     [rbp+57h+arg_8], r15
0x18000b7f3  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x18000b7f8  lea     rdx, [rbp+57h+arg_8]
0x18000b7fc  lea     rcx, [rbp+57h+var_88]
0x18000b800  call    ?Next@CSxIter@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@QEAAJPEAPEAVCSxStringEntry@@@Z; CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(CSxStringEntry * *)
0x18000b805  mov     [rbp+57h+var_70], eax
0x18000b808  mov     ecx, eax
0x18000b80a  test    eax, eax
0x18000b80c  js      short loc_18000B818
0x18000b80e  mov     [rbp+57h+var_6C], r12w
0x18000b813  jmp     loc_18000B794
0x18000b818  mov     [rbp+57h+var_6A], r12w
0x18000b81d  jmp     short loc_18000B83B
0x18000b81f  mov     [rbp+57h+var_6A], r13w
0x18000b824  jmp     short loc_18000B83B
0x18000b826  mov     rcx, [rbx+8]
0x18000b82a  mov     eax, [rbx+10h]
0x18000b82d  mov     [rbx+8], r15
0x18000b831  mov     [rbx+10h], r15
0x18000b835  mov     [rsi], rcx
0x18000b838  mov     [r14], eax
0x18000b83b  mov     rcx, [rbp+57h+pv]; pv
0x18000b83f  call    cs:__imp_CoTaskMemFree
0x18000b845  mov     edi, [rbp+57h+var_70]
0x18000b848  lea     rcx, [rbp+57h+var_98]; this
0x18000b84c  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000b851  test    rbx, rbx
0x18000b854  jz      short loc_18000B85E
0x18000b856  mov     rcx, rbx; Block
0x18000b859  call    ?Release@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@QEAAKXZ; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::Release(void)
0x18000b85e  mov     rcx, [rbp+57h+arg_8]; this
0x18000b862  test    rcx, rcx
0x18000b865  jz      short loc_18000B86C
0x18000b867  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x18000b86c  mov     rcx, [rbp+57h+var_80]; this
0x18000b870  test    rcx, rcx
0x18000b873  jz      short loc_18000B87E
0x18000b875  call    ?Release@CVolumeEntryMap@@QEAAKXZ; CVolumeEntryMap::Release(void)
0x18000b87a  mov     [rbp+57h+var_80], r15
0x18000b87e  lea     rcx, [rbp+57h+var_70]; this
0x18000b882  mov     [rbp+57h+var_88], r15d
0x18000b886  mov     [rbp+57h+var_80+8], r15
0x18000b88a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000b88f  mov     rbx, [rsp+0C0h+arg_0]
0x18000b897  mov     eax, edi
0x18000b899  add     rsp, 90h
0x18000b8a0  pop     r15
0x18000b8a2  pop     r14
0x18000b8a4  pop     r13
0x18000b8a6  pop     r12
0x18000b8a8  pop     rdi
0x18000b8a9  pop     rsi
0x18000b8aa  pop     rbp
0x18000b8ab  retn
```
