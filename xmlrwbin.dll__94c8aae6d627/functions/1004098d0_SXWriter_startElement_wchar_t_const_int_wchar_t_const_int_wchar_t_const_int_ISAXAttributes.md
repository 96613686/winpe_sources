# SXWriter::startElement(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,ISAXAttributes *)

- ea: `0x1004098d0`
- end: `0x100409d8c`
- name: `?startElement@SXWriter@@UEAAJPEB_WH0H0HPEAUISAXAttributes@@@Z`
- size: `1212`
- prototype: `int(SXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int, struct ISAXAttributes *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x100406e50`
- `0x100407330`
- `0x1004091f0`
- `0x1004093d0`
- `0x100409740`
- `0x100409840`
- `0x1004098d0`
- `0x100409da0`
- `0x10040adb0`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXWriter::startElement(
        SXWriter *this,
        wchar_t *a2,
        int a3,
        wchar_t *a4,
        int a5,
        wchar_t *a6,
        int a7,
        struct ISAXAttributes *a8)
{
  unsigned int v12; // edi
  unsigned int v13; // edx
  unsigned int v14; // eax
  unsigned int v15; // esi
  unsigned int i; // edx
  unsigned int v18; // ecx
  int j; // ebx
  __int64 v21; // [rsp+58h] [rbp-D0h] BYREF
  int v22; // [rsp+60h] [rbp-C8h] BYREF
  int v23; // [rsp+64h] [rbp-C4h] BYREF
  unsigned int v24; // [rsp+68h] [rbp-C0h]
  unsigned int v25; // [rsp+70h] [rbp-B8h] BYREF
  int v26; // [rsp+74h] [rbp-B4h] BYREF
  int v27; // [rsp+78h] [rbp-B0h] BYREF
  unsigned int v28; // [rsp+7Ch] [rbp-ACh] BYREF
  int v29; // [rsp+80h] [rbp-A8h] BYREF
  int v30; // [rsp+84h] [rbp-A4h] BYREF
  int v31[2]; // [rsp+88h] [rbp-A0h] BYREF
  int v32[4]; // [rsp+90h] [rbp-98h] BYREF
  _BYTE v33[40]; // [rsp+A0h] [rbp-88h] BYREF
  wchar_t *v34; // [rsp+C8h] [rbp-60h] BYREF
  wchar_t *v35; // [rsp+D0h] [rbp-58h] BYREF
  wchar_t *v36; // [rsp+D8h] [rbp-50h] BYREF
  unsigned __int64 *v37; // [rsp+E0h] [rbp-48h] BYREF
  wchar_t *v38; // [rsp+E8h] [rbp-40h] BYREF
  SXWriter *v39; // [rsp+F0h] [rbp-38h]

  v24 = 0;
  v21 = 0;
  if ( a2 )
  {
    if ( a4 )
    {
      if ( a6 )
      {
        if ( a5 > 0 )
        {
          _mm_lfence();
          v39 = (SXWriter *)((char *)this - 64);
          SXWriter::endAttributesCheck((SXWriter *)((char *)this - 64));
          Unitoken::Unitoken((Unitoken *)v33);
          v14 = v13 - 1;
          if ( a7 <= a5 )
            v14 = v13;
          SXWriter::getUnitokenFromNames(
            (SXWriter *)((char *)this - 64),
            a2,
            a3,
            a6,
            v14,
            a4,
            a5,
            &v25,
            (struct Unitoken *)v33);
          SXWriter::WriteByte((SXWriter *)((char *)this - 64), 0xF8u);
          SXWriter::WriteMb32((SXWriter *)((char *)this - 64), v25);
          if ( a8 )
          {
            ((void (__fastcall *)(struct ISAXAttributes *, GUID *, __int64 *))a8->lpVtbl->QueryInterface)(
              a8,
              &IID_ISXFormatAttributes,
              &v21);
            v12 = ((__int64 (__fastcall *)(struct ISAXAttributes *, int *))a8->lpVtbl->getLength)(a8, &v22);
            if ( !v12 )
            {
              v15 = 0;
              for ( i = 0; ; i = v15 )
              {
                v24 = v15;
                if ( !v22-- )
                  break;
                v12 = ((__int64 (__fastcall *)(struct ISAXAttributes *, _QWORD, wchar_t **, int *))a8->lpVtbl->getQName)(
                        a8,
                        v15,
                        &v34,
                        &v23);
                if ( v12 )
                  goto LABEL_40;
                v12 = ((__int64 (__fastcall *)(struct ISAXAttributes *, _QWORD, wchar_t **, int *))a8->lpVtbl->getLocalName)(
                        a8,
                        v15,
                        &v35,
                        &v26);
                if ( v12 )
                  goto LABEL_40;
                v12 = ((__int64 (__fastcall *)(struct ISAXAttributes *, _QWORD, wchar_t **, int *))a8->lpVtbl->getURI)(
                        a8,
                        v15,
                        &v36,
                        &v27);
                if ( v12 )
                  goto LABEL_40;
                if ( !v34 )
                {
LABEL_21:
                  v12 = -2147024809;
                  WriterHandleEntry::~WriterHandleEntry((WriterHandleEntry *)v33);
                  goto LABEL_41;
                }
                if ( v26 <= 0 || v23 <= v26 )
                  v18 = v23 - v26;
                else
                  v18 = v23 - v26 - 1;
                SXWriter::getUnitokenFromNames(
                  (SXWriter *)((char *)this - 64),
                  v36,
                  v27,
                  v34,
                  v18,
                  v35,
                  v26,
                  &v28,
                  (struct Unitoken *)v33);
                SXWriter::WriteByte((SXWriter *)((char *)this - 64), 0xF6u);
                SXWriter::WriteMb32((SXWriter *)((char *)this - 64), v28);
                if ( v21 )
                {
                  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v21 + 152LL))(v21, v15, &v29);
                  if ( v12 )
                    goto LABEL_40;
                  for ( j = 0; ; ++j )
                  {
                    v31[1] = j;
                    if ( j >= v29 )
                      break;
                    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, unsigned __int64 **, int *, int))(*(_QWORD *)v21 + 160LL))(
                            v21,
                            v15,
                            v31,
                            &v37,
                            &v30,
                            j);
                    if ( v12 )
                      goto LABEL_40;
                    SXWriter::WriteTypedData((__int64)this - 64, v31[0], v37, v30);
                  }
                }
                else
                {
                  v12 = ((__int64 (__fastcall *)(struct ISAXAttributes *, _QWORD, wchar_t **, int *))a8->lpVtbl->getValue)(
                          a8,
                          v15,
                          &v38,
                          v32);
                  if ( v12 )
                    goto LABEL_40;
                  if ( !v38 )
                    goto LABEL_21;
                  SXWriter::WriteTextData((SXWriter *)((char *)this - 64), 1, v38, v32[0]);
                }
                ++v15;
              }
              if ( i )
                SXWriter::WriteByte(v39, 0xF5u);
            }
          }
          else
          {
            v12 = 0;
          }
LABEL_40:
          WriterHandleEntry::~WriterHandleEntry((WriterHandleEntry *)v33);
        }
        else
        {
          v12 = -2147024809;
        }
      }
      else
      {
        v12 = -2147024809;
      }
    }
    else
    {
      v12 = -2147024809;
    }
  }
  else
  {
    v12 = -2147024809;
  }
LABEL_41:
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return v12;
}

```

## disassembly

```asm
0x1004098d0  mov     [rsp+arg_0], rbx
0x1004098d5  mov     [rsp+arg_8], rsi
0x1004098da  mov     [rsp+arg_10], rdi
0x1004098df  mov     [rsp+arg_18], r12
0x1004098e4  push    r13
0x1004098e6  push    r14
0x1004098e8  push    r15
0x1004098ea  sub     rsp, 110h
0x1004098f1  mov     rsi, r9
0x1004098f4  mov     r12d, r8d
0x1004098f7  mov     r14, rdx
0x1004098fa  mov     r13, rcx
0x1004098fd  mov     ebx, [rsp+128h+arg_20]
0x100409904  mov     r15d, [rsp+128h+arg_30]
0x10040990c  xor     eax, eax
0x10040990e  mov     [rsp+128h+var_D8], eax
0x100409912  mov     [rsp+128h+var_C0], eax
0x100409916  mov     [rsp+128h+var_D0], rax
0x10040991b  test    rdx, rdx
0x10040991e  jnz     short loc_10040992E
0x100409920  mov     edi, 80070057h
0x100409925  mov     [rsp+128h+var_D8], edi
0x100409929  jmp     loc_100409D51
0x10040992e  test    rsi, rsi
0x100409931  jnz     short loc_100409941
0x100409933  mov     edi, 80070057h
0x100409938  mov     [rsp+128h+var_D8], edi
0x10040993c  jmp     loc_100409D51
0x100409941  mov     rdi, [rsp+128h+arg_28]
0x100409949  test    rdi, rdi
0x10040994c  jnz     short loc_10040995C
0x10040994e  mov     edi, 80070057h
0x100409953  mov     [rsp+128h+var_D8], edi
0x100409957  jmp     loc_100409D51
0x10040995c  test    ebx, ebx
0x10040995e  jg      short loc_10040996E
0x100409960  mov     edi, 80070057h
0x100409965  mov     [rsp+128h+var_D8], edi
0x100409969  jmp     loc_100409D51
0x10040996e  lfence
0x100409971  add     rcx, 0FFFFFFFFFFFFFFC0h; this
0x100409975  mov     [rsp+128h+var_38], rcx
0x10040997d  call    ?endAttributesCheck@SXWriter@@AEAAXXZ; SXWriter::endAttributesCheck(void)
0x100409982  mov     edx, r15d
0x100409985  sub     edx, ebx
0x100409987  lea     rcx, [rsp+128h+var_88]; this
0x10040998f  call    ??0Unitoken@@QEAA@XZ; Unitoken::Unitoken(void)
0x100409994  lea     eax, [rdx-1]
0x100409997  cmp     r15d, ebx
0x10040999a  cmovle  eax, edx
0x10040999d  lea     rcx, [rsp+128h+var_88]
0x1004099a5  mov     [rsp+128h+var_E8], rcx; struct Unitoken *
0x1004099aa  lea     rcx, [rsp+128h+var_B8]
0x1004099af  mov     [rsp+128h+var_F0], rcx; unsigned int *
0x1004099b4  mov     [rsp+128h+var_F8], ebx; int
0x1004099b8  mov     [rsp+128h+var_100], rsi; wchar_t *
0x1004099bd  mov     dword ptr [rsp+128h+var_108], eax; int
0x1004099c1  mov     r9, rdi; wchar_t *
0x1004099c4  mov     r8d, r12d; int
0x1004099c7  mov     rdx, r14; wchar_t *
0x1004099ca  lea     rcx, [r13-40h]; this
0x1004099ce  call    ?getUnitokenFromNames@SXWriter@@AEAAXPEB_WH0H0HPEAKPEAVUnitoken@@@Z; SXWriter::getUnitokenFromNames(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,ulong *,Unitoken *)
0x1004099d3  mov     dl, 0F8h; unsigned __int8
0x1004099d5  lea     rcx, [r13-40h]; this
0x1004099d9  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x1004099de  mov     edx, [rsp+128h+var_B8]; unsigned int
0x1004099e2  lea     rcx, [r13-40h]; this
0x1004099e6  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x1004099eb  mov     r15, [rsp+128h+arg_38]
0x1004099f3  test    r15, r15
0x1004099f6  jz      loc_100409D16
0x1004099fc  mov     rax, [r15]
0x1004099ff  lea     r8, [rsp+128h+var_D0]
0x100409a04  lea     rdx, IID_ISXFormatAttributes
0x100409a0b  mov     rcx, r15
0x100409a0e  mov     rax, [rax]
0x100409a11  call    cs:__guard_dispatch_icall_fptr
0x100409a17  mov     rax, [r15]
0x100409a1a  lea     rdx, [rsp+128h+var_C8]
0x100409a1f  mov     rcx, r15
0x100409a22  mov     rax, [rax+18h]
0x100409a26  call    cs:__guard_dispatch_icall_fptr
0x100409a2c  mov     edi, eax
0x100409a2e  mov     [rsp+128h+var_D8], eax
0x100409a32  test    eax, eax
0x100409a34  jz      short loc_100409A48
0x100409a36  lea     rcx, [rsp+128h+var_88]; this
0x100409a3e  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x100409a43  jmp     loc_100409D51
0x100409a48  xor     esi, esi
0x100409a4a  xor     edx, edx
0x100409a4c  mov     [rsp+128h+var_C0], esi
0x100409a50  mov     eax, [rsp+128h+var_C8]
0x100409a54  mov     ecx, eax
0x100409a56  dec     eax
0x100409a58  mov     [rsp+128h+var_C8], eax
0x100409a5c  test    ecx, ecx
0x100409a5e  jz      loc_100409D01
0x100409a64  mov     rax, [r15]
0x100409a67  lea     r9, [rsp+128h+var_C4]
0x100409a6c  lea     r8, [rsp+128h+var_60]
0x100409a74  mov     edx, esi
0x100409a76  mov     rcx, r15
0x100409a79  mov     rax, [rax+30h]
0x100409a7d  call    cs:__guard_dispatch_icall_fptr
0x100409a83  mov     edi, eax
0x100409a85  mov     [rsp+128h+var_D8], eax
0x100409a89  test    eax, eax
0x100409a8b  jz      short loc_100409A9F
0x100409a8d  lea     rcx, [rsp+128h+var_88]; this
0x100409a95  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x100409a9a  jmp     loc_100409D51
0x100409a9f  mov     rax, [r15]
0x100409aa2  lea     r9, [rsp+128h+var_B4]
0x100409aa7  lea     r8, [rsp+128h+var_58]
0x100409aaf  mov     edx, esi
0x100409ab1  mov     rcx, r15
0x100409ab4  mov     rax, [rax+28h]
0x100409ab8  call    cs:__guard_dispatch_icall_fptr
0x100409abe  mov     edi, eax
0x100409ac0  mov     [rsp+128h+var_D8], eax
0x100409ac4  test    eax, eax
0x100409ac6  jz      short loc_100409ADA
0x100409ac8  lea     rcx, [rsp+128h+var_88]; this
0x100409ad0  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x100409ad5  jmp     loc_100409D51
0x100409ada  mov     rax, [r15]
0x100409add  lea     r9, [rsp+128h+var_B0]
0x100409ae2  lea     r8, [rsp+128h+var_50]
0x100409aea  mov     edx, esi
0x100409aec  mov     rcx, r15
0x100409aef  mov     rax, [rax+20h]
0x100409af3  call    cs:__guard_dispatch_icall_fptr
0x100409af9  mov     edi, eax
0x100409afb  mov     [rsp+128h+var_D8], eax
0x100409aff  test    eax, eax
0x100409b01  jz      short loc_100409B15
0x100409b03  lea     rcx, [rsp+128h+var_88]; this
0x100409b0b  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x100409b10  jmp     loc_100409D51
0x100409b15  mov     r9, [rsp+128h+var_60]; wchar_t *
0x100409b1d  test    r9, r9
0x100409b20  jnz     short loc_100409B3D
0x100409b22  mov     edi, 80070057h
0x100409b27  mov     [rsp+128h+var_D8], edi
0x100409b2b  lea     rcx, [rsp+128h+var_88]; this
0x100409b33  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x100409b38  jmp     loc_100409D51
0x100409b3d  mov     eax, [rsp+128h+var_B4]
0x100409b41  mov     ecx, [rsp+128h+var_C4]
0x100409b45  test    eax, eax
0x100409b47  jle     short loc_100409B53
0x100409b49  cmp     ecx, eax
0x100409b4b  jle     short loc_100409B53
0x100409b4d  sub     ecx, eax
0x100409b4f  dec     ecx
0x100409b51  jmp     short loc_100409B55
0x100409b53  sub     ecx, eax
0x100409b55  lea     rdx, [rsp+128h+var_88]
0x100409b5d  mov     [rsp+128h+var_E8], rdx; struct Unitoken *
0x100409b62  lea     rdx, [rsp+128h+var_AC]
0x100409b67  mov     [rsp+128h+var_F0], rdx; unsigned int *
0x100409b6c  mov     [rsp+128h+var_F8], eax; int
0x100409b70  mov     rax, [rsp+128h+var_58]
0x100409b78  mov     [rsp+128h+var_100], rax; wchar_t *
0x100409b7d  mov     dword ptr [rsp+128h+var_108], ecx; bool
0x100409b81  mov     r8d, [rsp+128h+var_B0]; int
0x100409b86  mov     rdx, [rsp+128h+var_50]; wchar_t *
0x100409b8e  lea     rcx, [r13-40h]; this
0x100409b92  call    ?getUnitokenFromNames@SXWriter@@AEAAXPEB_WH0H0HPEAKPEAVUnitoken@@@Z; SXWriter::getUnitokenFromNames(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,ulong *,Unitoken *)
0x100409b97  mov     dl, 0F6h; unsigned __int8
0x100409b99  lea     rcx, [r13-40h]; this
0x100409b9d  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x100409ba2  mov     edx, [rsp+128h+var_AC]; unsigned int
0x100409ba6  lea     rcx, [r13-40h]; this
0x100409baa  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x100409baf  mov     rcx, [rsp+128h+var_D0]
0x100409bb4  mov     edx, esi
0x100409bb6  test    rcx, rcx
0x100409bb9  jz      loc_100409C84
0x100409bbf  mov     rax, [rcx]
0x100409bc2  lea     r8, [rsp+128h+var_A8]
0x100409bca  mov     rax, [rax+98h]
0x100409bd1  call    cs:__guard_dispatch_icall_fptr
0x100409bd7  mov     edi, eax
0x100409bd9  mov     [rsp+128h+var_D8], eax
0x100409bdd  test    eax, eax
0x100409bdf  jz      short loc_100409BF3
0x100409be1  lea     rcx, [rsp+128h+var_88]; this
0x100409be9  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x100409bee  jmp     loc_100409D51
0x100409bf3  xor     ebx, ebx
0x100409bf5  mov     [rsp+128h+var_9C], ebx
0x100409bfc  cmp     ebx, [rsp+128h+var_A8]
0x100409c03  jge     loc_100409CF8
0x100409c09  mov     rcx, [rsp+128h+var_D0]
0x100409c0e  mov     rax, [rcx]
0x100409c11  mov     dword ptr [rsp+128h+var_100], ebx
0x100409c15  lea     rdx, [rsp+128h+var_A4]
0x100409c1d  mov     qword ptr [rsp+128h+var_108], rdx
0x100409c22  lea     r9, [rsp+128h+var_48]
0x100409c2a  lea     r8, [rsp+128h+var_A0]
0x100409c32  mov     edx, esi
0x100409c34  mov     rax, [rax+0A0h]
0x100409c3b  call    cs:__guard_dispatch_icall_fptr
0x100409c41  mov     edi, eax
0x100409c43  mov     [rsp+128h+var_D8], eax
0x100409c47  test    eax, eax
0x100409c49  jz      short loc_100409C5D
0x100409c4b  lea     rcx, [rsp+128h+var_88]; this
0x100409c53  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x100409c58  jmp     loc_100409D51
0x100409c5d  mov     r9d, [rsp+128h+var_A4]
0x100409c65  mov     r8, [rsp+128h+var_48]
0x100409c6d  mov     edx, [rsp+128h+var_A0]
0x100409c74  lea     rcx, [r13-40h]
0x100409c78  call    ?WriteTypedData@SXWriter@@AEAAXW4tagSXFORMATTYPE@@PEBXH@Z; SXWriter::WriteTypedData(tagSXFORMATTYPE,void const *,int)
0x100409c7d  inc     ebx
0x100409c7f  jmp     loc_100409BF5
0x100409c84  mov     rax, [r15]
0x100409c87  lea     r9, [rsp+128h+var_98]
0x100409c8f  lea     r8, [rsp+128h+var_40]
0x100409c97  mov     rcx, r15
0x100409c9a  mov     rax, [rax+68h]
0x100409c9e  call    cs:__guard_dispatch_icall_fptr
0x100409ca4  mov     edi, eax
0x100409ca6  mov     [rsp+128h+var_D8], eax
0x100409caa  test    eax, eax
0x100409cac  jz      short loc_100409CC0
0x100409cae  lea     rcx, [rsp+128h+var_88]; this
0x100409cb6  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x100409cbb  jmp     loc_100409D51
0x100409cc0  mov     r8, [rsp+128h+var_40]; wchar_t *
0x100409cc8  test    r8, r8
0x100409ccb  jnz     short loc_100409CE5
0x100409ccd  mov     edi, 80070057h
0x100409cd2  mov     [rsp+128h+var_D8], edi
0x100409cd6  lea     rcx, [rsp+128h+var_88]; this
0x100409cde  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x100409ce3  jmp     short loc_100409D51
0x100409ce5  mov     r9d, [rsp+128h+var_98]; int
0x100409ced  mov     dl, 1; bool
0x100409cef  lea     rcx, [r13-40h]; this
0x100409cf3  call    ?WriteTextData@SXWriter@@AEAAX_NPEB_WH0@Z; SXWriter::WriteTextData(bool,wchar_t const *,int,bool)
0x100409cf8  inc     esi
0x100409cfa  mov     edx, esi
0x100409cfc  jmp     loc_100409A4C
0x100409d01  test    edx, edx
0x100409d03  jz      short loc_100409D1A
0x100409d05  mov     dl, 0F5h; unsigned __int8
0x100409d07  mov     rcx, [rsp+128h+var_38]; this
0x100409d0f  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x100409d14  jmp     short loc_100409D1A
0x100409d16  mov     edi, [rsp+128h+var_D8]
0x100409d1a  lea     rcx, [rsp+128h+var_88]; this
0x100409d22  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x100409d27  jmp     short loc_100409D51
0x100409d29  mov     rcx, [rsp+128h+var_D0]
0x100409d2e  test    rcx, rcx
0x100409d31  jz      short loc_100409D49
0x100409d33  mov     rax, [rcx]
0x100409d36  mov     rax, [rax+10h]
0x100409d3a  call    cs:__guard_dispatch_icall_fptr
0x100409d40  mov     [rsp+128h+var_D0], 0
0x100409d49  mov     edi, [rsp+128h+var_D4]
0x100409d4d  mov     [rsp+128h+var_D8], edi
0x100409d51  mov     rcx, [rsp+128h+var_D0]
0x100409d56  test    rcx, rcx
0x100409d59  jz      short loc_100409D68
0x100409d5b  mov     rax, [rcx]
0x100409d5e  mov     rax, [rax+10h]
0x100409d62  call    cs:__guard_dispatch_icall_fptr
0x100409d68  mov     eax, edi
0x100409d6a  lea     r11, [rsp+128h+var_18]
0x100409d72  mov     rbx, [r11+20h]
0x100409d76  mov     rsi, [r11+28h]
0x100409d7a  mov     rdi, [r11+30h]
0x100409d7e  mov     r12, [r11+38h]
0x100409d82  mov     rsp, r11
0x100409d85  pop     r15
0x100409d87  pop     r14
0x100409d89  pop     r13
0x100409d8b  retn
0x1004248d0  push    rbp
0x1004248d2  sub     rsp, 50h
0x1004248d6  mov     rbp, rdx
0x1004248d9  mov     [rbp+100h], rcx
0x1004248e0  mov     [rbp+0F8h], rcx
0x1004248e7  mov     rax, [rbp+0F8h]
0x1004248ee  mov     rcx, [rax]
0x1004248f1  mov     [rbp+98h], rcx
0x1004248f8  mov     rax, [rbp+98h]
0x1004248ff  mov     eax, [rax]
0x100424901  cmp     eax, 0C0000005h
0x100424906  jz      short loc_10042493E
0x100424908  add     eax, 1FFFFFFFh
0x10042490d  cmp     eax, 1
0x100424910  ja      short loc_10042492E
0x100424912  mov     rax, [rbp+98h]
0x100424919  cmp     dword ptr [rax+18h], 1
  ... truncated ...
```
