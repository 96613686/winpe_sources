# VmpSetGptAttributes(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140013e00`
- end: `0x140014399`
- name: `?VmpSetGptAttributes@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `1433`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140002db0`
- `0x1400031b0`
- `0x140005050`
- `0x140005090`
- `0x140005540`
- `0x14000f56c`
- `0x140011bd8`
- `0x140011d94`
- `0x1400130b0`
- `0x140013ba0`
- `0x140013e00`
- `0x1400143a0`
- `0x140015a70`

## pseudocode

```c
int __fastcall VmpSetGptAttributes(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  __int64 v2; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  __int64 v6; // rsi
  bool v7; // cf
  unsigned int v8; // r14d
  struct _IRP *MasterIrp; // rdi
  __int64 v10; // rax
  unsigned __int64 v11; // r14
  int result; // eax
  int v13; // eax
  char MdlAddress; // cl
  int v15; // esi
  struct _GUID *v16; // r9
  char v17; // dl
  struct _GUID *v18; // r8
  char v19; // cl
  struct _DEVICE_OBJECT *v20; // rcx
  unsigned __int8 v21; // r8
  PFILE_OBJECT FileObject; // rax
  unsigned __int64 v23; // rcx
  int v24; // eax
  char v25; // cl
  _QWORD *v26; // r12
  _QWORD *i; // r14
  _QWORD *v28; // rsi
  int v29; // r15d
  int GptAttributes; // eax
  unsigned __int8 v31; // r8
  char v32; // cl
  int v33; // eax
  bool v34; // zf
  unsigned __int64 v35; // rsi
  struct _DEVICE_OBJECT *v36; // rcx
  int v37; // eax
  char v38; // cl
  _QWORD **v39; // r15
  _QWORD *j; // rsi
  _QWORD *v41; // r14
  unsigned int v42; // [rsp+20h] [rbp-A9h]
  unsigned int v43; // [rsp+30h] [rbp-99h] BYREF
  unsigned __int64 v44; // [rsp+38h] [rbp-91h] BYREF
  struct _GUID v45; // [rsp+40h] [rbp-89h] BYREF
  _DWORD v46[36]; // [rsp+50h] [rbp-79h] BYREF

  v2 = *((_QWORD *)a1 + 1);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v6 = *(_QWORD *)(v2 + 392);
  v45 = 0;
  v44 = 0;
  memset(v46, 0, sizeof(v46));
  v7 = CurrentStackLocation->Parameters.Create.Options < 0x10;
  v8 = 0;
  v43 = 0;
  if ( !v7 )
  {
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    if ( !WORD1(MasterIrp->MdlAddress) && !HIDWORD(MasterIrp->MdlAddress) )
    {
      if ( *((_BYTE *)a1 + 426) )
      {
        if ( *((_QWORD *)a1 + 54) )
        {
          if ( (*(_QWORD *)&MasterIrp->Type & 0x400000000000000LL) == 0
            && ((*(_QWORD *)&MasterIrp->Type & 0x800000000000000LL) == 0
             || (*(_DWORD *)(*(_QWORD *)a1 + 48LL) & 0x600100) == 0 && !*((_DWORD *)a1 + 37)) )
          {
            if ( !BYTE1(MasterIrp->MdlAddress) )
            {
              v10 = (*(__int64 (__fastcall **)(_QWORD))(v6 + 152))(*((_QWORD *)a1 + 54));
              v11 = v10;
              if ( LOBYTE(MasterIrp->MdlAddress) )
              {
                *((_QWORD *)a1 + 40) = CurrentStackLocation->FileObject;
                *((_QWORD *)a1 + 41) = v10;
                *((_BYTE *)a1 + 336) = BYTE1(MasterIrp->MdlAddress);
                (*(void (__fastcall **)(_QWORD, struct _GUID *))(v6 + 120))(*((_QWORD *)a1 + 54), &v45);
                result = VmpStoreGptAttributesRevertRecord(1, 0, &v45, 0, 0, v11);
                if ( result < 0 )
                {
LABEL_13:
                  *((_QWORD *)a1 + 40) = 0;
                  return result;
                }
              }
              v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v6 + 176))(
                      *((_QWORD *)a1 + 54),
                      *(_QWORD *)&MasterIrp->Type,
                      0);
              MdlAddress = (char)MasterIrp->MdlAddress;
              v15 = v13;
              if ( v13 < 0 )
              {
                if ( !MdlAddress )
                  return v15;
                v16 = 0;
                v42 = 0;
                v17 = 0;
                v18 = &v45;
                v19 = 1;
LABEL_17:
                *((_QWORD *)a1 + 40) = 0;
                VmpDeleteGptAttributesRevertRecord(v19, v17, v18, v16, v42);
                return v15;
              }
              if ( !MdlAddress )
                VmpApplyGptAttributes(a1, *(_QWORD *)&MasterIrp->Type);
              return 0;
            }
            return -1073741811;
          }
          return -1073741808;
        }
        return -1073741810;
      }
      v20 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 43);
      if ( !v20 )
        return -1073741810;
      result = VmpSendDeviceControl(v20, 0x70048u, 0, 0, v46, 0x90u);
      if ( result < 0 )
        return result;
      if ( SC_PART_ENTRY::IsRecognized((SC_PART_ENTRY *)v46) )
      {
        if ( _bittest64((const signed __int64 *)&MasterIrp->Type, 0x3Bu)
          && (BYTE1(MasterIrp->MdlAddress) || (*(_DWORD *)(*(_QWORD *)a1 + 48LL) & 0x600100) != 0
                                           || *((_DWORD *)a1 + 37))
          || (*(_QWORD *)&MasterIrp->Type & 0x600000000000000LL) != 0 && BYTE1(MasterIrp->MdlAddress) )
        {
          return -1073741808;
        }
        result = VmpDiskGetGptAttributes(*((struct _DEVICE_OBJECT **)a1 + 43), &v44);
        if ( result < 0 )
          return result;
        if ( v46[0] == 1 )
        {
          if ( LOBYTE(MasterIrp->MdlAddress) )
          {
            FileObject = CurrentStackLocation->FileObject;
            v23 = v44;
            *((_QWORD *)a1 + 41) = v44;
            *((_QWORD *)a1 + 40) = FileObject;
            *((_BYTE *)a1 + 336) = BYTE1(MasterIrp->MdlAddress);
            result = VmpStoreGptAttributesRevertRecord(0, 1, 0, (struct _GUID *)((char *)a1 + 408), 0, v23);
            if ( result < 0 )
              goto LABEL_13;
          }
          v24 = VmpDiskSetGptAttributes(*((struct _DEVICE_OBJECT **)a1 + 43), *(_QWORD *)&MasterIrp->Type, v21);
          v25 = (char)MasterIrp->MdlAddress;
          v15 = v24;
          if ( v24 < 0 )
          {
            if ( !v25 )
              return v15;
            v16 = (struct _GUID *)((char *)a1 + 408);
            v42 = 0;
            v18 = 0;
            v17 = 1;
            goto LABEL_39;
          }
          if ( !v25 )
            VmpApplyGptAttributes(a1, *(_QWORD *)&MasterIrp->Type);
          if ( BYTE1(MasterIrp->MdlAddress) )
          {
            v26 = (_QWORD *)(v2 + 208);
            for ( i = *(_QWORD **)(v2 + 208); ; i = (_QWORD *)*i )
            {
              if ( i == v26 )
                return 0;
              v28 = i - 4;
              if ( i - 4 != (_QWORD *)a1 && !*((_BYTE *)v28 + 426) && v28[45] == *((_QWORD *)a1 + 45) )
              {
                v29 = VmpSendDeviceControl((PDEVICE_OBJECT)v28[43], 0x70048u, 0, 0, v46, 0x90u);
                if ( v29 < 0 )
                  goto LABEL_59;
                if ( SC_PART_ENTRY::IsRecognized((SC_PART_ENTRY *)v46) )
                {
                  GptAttributes = VmpDiskGetGptAttributes((struct _DEVICE_OBJECT *)v28[43], &v44);
                  v32 = (char)MasterIrp->MdlAddress;
                  v29 = GptAttributes;
                  if ( GptAttributes < 0 )
                    goto LABEL_58;
                  if ( v32 )
                  {
                    v29 = VmpStoreGptAttributesRevertRecord(0, 1, 0, (struct _GUID *)(v28 + 51), 0, v44);
                    if ( v29 < 0 )
                    {
LABEL_59:
                      v34 = LOBYTE(MasterIrp->MdlAddress) == 0;
                      goto LABEL_60;
                    }
                  }
                  v33 = VmpDiskSetGptAttributes((struct _DEVICE_OBJECT *)v28[43], *(_QWORD *)&MasterIrp->Type, v31);
                  v32 = (char)MasterIrp->MdlAddress;
                  v29 = v33;
                  if ( v33 < 0 )
                  {
LABEL_58:
                    v34 = v32 == 0;
LABEL_60:
                    if ( !v34 )
                      VmpRevertGptAttributes(a1);
                    return v29;
                  }
                  if ( !v32 )
                    VmpApplyGptAttributes((struct VM_VOLUME_EXTENSION *)(i - 4), *(_QWORD *)&MasterIrp->Type);
                }
              }
            }
          }
          return 0;
        }
        if ( v46[0] )
          return -1073741823;
        if ( BYTE1(MasterIrp->MdlAddress) )
        {
          if ( LOBYTE(MasterIrp->MdlAddress) )
          {
            v35 = v44;
            v36 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 45);
            *((_QWORD *)a1 + 40) = CurrentStackLocation->FileObject;
            *((_QWORD *)a1 + 41) = v35;
            *((_BYTE *)a1 + 336) = BYTE1(MasterIrp->MdlAddress);
            result = VmpQueryDiskSignature(v36, &v43);
            if ( result < 0 )
              goto LABEL_13;
            v8 = v43;
            result = VmpStoreGptAttributesRevertRecord(0, 0, 0, 0, v43, v35);
            if ( result < 0 )
              goto LABEL_13;
          }
          v37 = VmpDiskSetGptAttributes(*((struct _DEVICE_OBJECT **)a1 + 43), *(_QWORD *)&MasterIrp->Type, v21);
          v38 = (char)MasterIrp->MdlAddress;
          v15 = v37;
          if ( v37 < 0 )
          {
            if ( !v38 )
              return v15;
            v16 = 0;
            v42 = v8;
            v18 = 0;
            v17 = 0;
LABEL_39:
            v19 = 0;
            goto LABEL_17;
          }
          if ( !v38 )
          {
            VmpApplyGptAttributes(a1, *(_QWORD *)&MasterIrp->Type);
            v39 = (_QWORD **)(v2 + 208);
            for ( j = *v39; j != v39; j = (_QWORD *)*j )
            {
              v41 = j - 4;
              if ( j - 4 != (_QWORD *)a1
                && !*((_BYTE *)v41 + 426)
                && v41[45] == *((_QWORD *)a1 + 45)
                && VmpSendDeviceControl((PDEVICE_OBJECT)v41[43], 0x70048u, 0, 0, v46, 0x90u) >= 0
                && SC_PART_ENTRY::IsRecognized((SC_PART_ENTRY *)v46) )
              {
                VmpApplyGptAttributes((struct VM_VOLUME_EXTENSION *)(j - 4), *(_QWORD *)&MasterIrp->Type);
              }
            }
          }
          return 0;
        }
      }
    }
  }
  return -1073741811;
}

```

## disassembly

```asm
0x140013e00  mov     [rsp-8+arg_10], rbx
0x140013e05  push    rbp
0x140013e06  push    rsi
0x140013e07  push    rdi
0x140013e08  push    r12
0x140013e0a  push    r13
0x140013e0c  push    r14
0x140013e0e  push    r15
0x140013e10  lea     rbp, [rsp-27h]
0x140013e15  sub     rsp, 0F0h
0x140013e1c  mov     rax, cs:__security_cookie
0x140013e23  xor     rax, rsp
0x140013e26  mov     [rbp+57h+var_40], rax
0x140013e2a  mov     r15, [rcx+8]
0x140013e2e  mov     rdi, rdx
0x140013e31  mov     r13, [rdx+0B8h]
0x140013e38  mov     rbx, rcx
0x140013e3b  xorps   xmm0, xmm0
0x140013e3e  lea     rcx, [rbp+57h+var_D0]; void *
0x140013e42  xor     r12d, r12d
0x140013e45  xor     edx, edx; Val
0x140013e47  mov     rsi, [r15+188h]
0x140013e4e  mov     r8d, 90h; Size
0x140013e54  movups  xmmword ptr [rsp+120h+var_E0.Data1], xmm0
0x140013e59  mov     [rsp+120h+var_E8], r12
0x140013e5e  call    memset
0x140013e63  cmp     dword ptr [r13+10h], 10h
0x140013e68  mov     r14d, r12d
0x140013e6b  mov     [rsp+120h+var_F0], r12d
0x140013e70  jb      loc_14001436C
0x140013e76  mov     rdi, [rdi+18h]
0x140013e7a  cmp     [rdi+0Ah], r12w
0x140013e7f  jnz     loc_14001436C
0x140013e85  cmp     [rdi+0Ch], r12d
0x140013e89  jnz     loc_14001436C
0x140013e8f  cmp     [rbx+1AAh], r12b
0x140013e96  jz      loc_140013FC0
0x140013e9c  cmp     [rbx+1B0h], r12
0x140013ea3  jz      loc_140013FCC
0x140013ea9  mov     rax, [rdi]
0x140013eac  bt      rax, 3Ah ; ':'
0x140013eb1  jb      loc_140014049
0x140013eb7  bt      rax, 3Bh ; ';'
0x140013ebc  jnb     short loc_140013EDD
0x140013ebe  mov     rax, [rbx]
0x140013ec1  mov     ecx, [rax+30h]
0x140013ec4  test    ecx, 600100h
0x140013eca  jnz     loc_140014049
0x140013ed0  cmp     [rbx+94h], r12d
0x140013ed7  jnz     loc_140014049
0x140013edd  cmp     [rdi+9], r12b
0x140013ee1  jnz     loc_14001436C
0x140013ee7  mov     rax, [rsi+98h]
0x140013eee  mov     rcx, [rbx+1B0h]
0x140013ef5  call    _guard_dispatch_icall
0x140013efa  mov     r14, rax
0x140013efd  cmp     [rdi+8], r12b
0x140013f01  jz      short loc_140013F5E
0x140013f03  mov     rcx, [r13+30h]
0x140013f07  lea     rdx, [rsp+120h+var_E0]
0x140013f0c  mov     [rbx+140h], rcx
0x140013f13  mov     [rbx+148h], rax
0x140013f1a  mov     cl, [rdi+9]
0x140013f1d  mov     [rbx+150h], cl
0x140013f23  mov     rax, [rsi+78h]
0x140013f27  mov     rcx, [rbx+1B0h]
0x140013f2e  call    _guard_dispatch_icall
0x140013f33  xor     r9d, r9d; struct _GUID *
0x140013f36  mov     qword ptr [rsp+120h+var_F8], r14; unsigned __int64
0x140013f3b  lea     r8, [rsp+120h+var_E0]; struct _GUID *
0x140013f40  mov     dword ptr [rsp+120h+var_100], r12d; unsigned int
0x140013f45  xor     edx, edx; unsigned __int8
0x140013f47  mov     cl, 1; unsigned __int8
0x140013f49  call    ?VmpStoreGptAttributesRevertRecord@@YAJEEPEAU_GUID@@0K_K@Z; VmpStoreGptAttributesRevertRecord(uchar,uchar,_GUID *,_GUID *,ulong,unsigned __int64)
0x140013f4e  test    eax, eax
0x140013f50  jns     short loc_140013F5E
0x140013f52  mov     [rbx+140h], r12
0x140013f59  jmp     loc_140014371
0x140013f5e  mov     rax, [rsi+0B0h]
0x140013f65  xor     r8d, r8d
0x140013f68  mov     rdx, [rdi]
0x140013f6b  mov     rcx, [rbx+1B0h]
0x140013f72  call    _guard_dispatch_icall
0x140013f77  mov     cl, [rdi+8]
0x140013f7a  mov     esi, eax
0x140013f7c  test    eax, eax
0x140013f7e  jns     short loc_140013FA8
0x140013f80  test    cl, cl
0x140013f82  jz      short loc_140013FA1
0x140013f84  xor     r9d, r9d; struct _GUID *
0x140013f87  mov     dword ptr [rsp+120h+var_100], r12d; unsigned int
0x140013f8c  xor     edx, edx; unsigned __int8
0x140013f8e  lea     r8, [rsp+120h+var_E0]; struct _GUID *
0x140013f93  mov     cl, 1; unsigned __int8
0x140013f95  mov     [rbx+140h], r12
0x140013f9c  call    ?VmpDeleteGptAttributesRevertRecord@@YAXEEPEAU_GUID@@0K@Z; VmpDeleteGptAttributesRevertRecord(uchar,uchar,_GUID *,_GUID *,ulong)
0x140013fa1  mov     eax, esi
0x140013fa3  jmp     loc_140014371
0x140013fa8  test    cl, cl
0x140013faa  jnz     loc_140014110
0x140013fb0  mov     rdx, [rdi]; unsigned __int64
0x140013fb3  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140013fb6  call    ?VmpApplyGptAttributes@@YAXPEAVVM_VOLUME_EXTENSION@@_K@Z; VmpApplyGptAttributes(VM_VOLUME_EXTENSION *,unsigned __int64)
0x140013fbb  jmp     loc_140014110
0x140013fc0  mov     rcx, [rbx+158h]; DeviceObject
0x140013fc7  test    rcx, rcx
0x140013fca  jnz     short loc_140013FD6
0x140013fcc  mov     eax, 0C000000Eh
0x140013fd1  jmp     loc_140014371
0x140013fd6  lea     rax, [rbp+57h+var_D0]
0x140013fda  mov     [rsp+120h+var_F8], 90h; ULONG
0x140013fe2  xor     r9d, r9d; InputBufferLength
0x140013fe5  mov     [rsp+120h+var_100], rax; PVOID
0x140013fea  xor     r8d, r8d; InputBuffer
0x140013fed  mov     edx, 70048h; IoControlCode
0x140013ff2  call    VmpSendDeviceControl
0x140013ff7  test    eax, eax
0x140013ff9  js      loc_140014371
0x140013fff  lea     rcx, [rbp+57h+var_D0]; this
0x140014003  call    ?IsRecognized@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsRecognized(void)
0x140014008  test    al, al
0x14001400a  jz      loc_14001436C
0x140014010  bt      qword ptr [rdi], 3Bh ; ';'
0x140014015  jnb     short loc_140014034
0x140014017  cmp     [rdi+9], r12b
0x14001401b  jnz     short loc_140014049
0x14001401d  mov     rax, [rbx]
0x140014020  mov     ecx, [rax+30h]
0x140014023  test    ecx, 600100h
0x140014029  jnz     short loc_140014049
0x14001402b  cmp     [rbx+94h], r12d
0x140014032  jnz     short loc_140014049
0x140014034  mov     rcx, 600000000000000h
0x14001403e  test    [rdi], rcx
0x140014041  jz      short loc_140014053
0x140014043  cmp     [rdi+9], r12b
0x140014047  jz      short loc_140014053
0x140014049  mov     eax, 0C0000010h
0x14001404e  jmp     loc_140014371
0x140014053  mov     rcx, [rbx+158h]; struct _DEVICE_OBJECT *
0x14001405a  lea     rdx, [rsp+120h+var_E8]; unsigned __int64 *
0x14001405f  call    ?VmpDiskGetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@PEA_K@Z; VmpDiskGetGptAttributes(_DEVICE_OBJECT *,unsigned __int64 *)
0x140014064  test    eax, eax
0x140014066  js      loc_140014371
0x14001406c  mov     eax, [rbp+57h+var_D0]
0x14001406f  cmp     eax, 1
0x140014072  jnz     loc_14001422A
0x140014078  cmp     [rdi+8], r12b
0x14001407c  jz      short loc_1400140C3
0x14001407e  mov     rax, [r13+30h]
0x140014082  lea     r9, [rbx+198h]; struct _GUID *
0x140014089  mov     rcx, [rsp+120h+var_E8]
0x14001408e  xor     r8d, r8d; struct _GUID *
0x140014091  mov     [rbx+148h], rcx
0x140014098  mov     dl, 1; unsigned __int8
0x14001409a  mov     qword ptr [rsp+120h+var_F8], rcx; unsigned __int64
0x14001409f  xor     ecx, ecx; unsigned __int8
0x1400140a1  mov     [rbx+140h], rax
0x1400140a8  mov     al, [rdi+9]
0x1400140ab  mov     [rbx+150h], al
0x1400140b1  mov     dword ptr [rsp+120h+var_100], r12d; unsigned int
0x1400140b6  call    ?VmpStoreGptAttributesRevertRecord@@YAJEEPEAU_GUID@@0K_K@Z; VmpStoreGptAttributesRevertRecord(uchar,uchar,_GUID *,_GUID *,ulong,unsigned __int64)
0x1400140bb  test    eax, eax
0x1400140bd  js      loc_140013F52
0x1400140c3  mov     rdx, [rdi]; unsigned __int64
0x1400140c6  mov     rcx, [rbx+158h]; struct _DEVICE_OBJECT *
0x1400140cd  call    ?VmpDiskSetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@_KE@Z; VmpDiskSetGptAttributes(_DEVICE_OBJECT *,unsigned __int64,uchar)
0x1400140d2  mov     cl, [rdi+8]
0x1400140d5  mov     esi, eax
0x1400140d7  test    eax, eax
0x1400140d9  jns     short loc_1400140FB
0x1400140db  test    cl, cl
0x1400140dd  jz      loc_140013FA1
0x1400140e3  lea     r9, [rbx+198h]
0x1400140ea  mov     dword ptr [rsp+120h+var_100], r12d
0x1400140ef  xor     r8d, r8d
0x1400140f2  mov     dl, 1
0x1400140f4  xor     ecx, ecx
0x1400140f6  jmp     loc_140013F95
0x1400140fb  test    cl, cl
0x1400140fd  jnz     short loc_14001410A
0x1400140ff  mov     rdx, [rdi]; unsigned __int64
0x140014102  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x140014105  call    ?VmpApplyGptAttributes@@YAXPEAVVM_VOLUME_EXTENSION@@_K@Z; VmpApplyGptAttributes(VM_VOLUME_EXTENSION *,unsigned __int64)
0x14001410a  cmp     [rdi+9], r12b
0x14001410e  jnz     short loc_140014117
0x140014110  xor     eax, eax
0x140014112  jmp     loc_140014371
0x140014117  lea     r12, [r15+0D0h]
0x14001411e  xor     r13d, r13d
0x140014121  mov     r14, [r12]
0x140014125  cmp     r14, r12
0x140014128  jz      short loc_140014110
0x14001412a  lea     rsi, [r14-20h]
0x14001412e  cmp     rsi, rbx
0x140014131  jz      loc_140014208
0x140014137  cmp     [rsi+1AAh], r13b
0x14001413e  jnz     loc_140014208
0x140014144  mov     rax, [rbx+168h]
0x14001414b  cmp     [rsi+168h], rax
0x140014152  jnz     loc_140014208
0x140014158  mov     rcx, [rsi+158h]; DeviceObject
0x14001415f  lea     rax, [rbp+57h+var_D0]
0x140014163  mov     [rsp+120h+var_F8], 90h; ULONG
0x14001416b  xor     r9d, r9d; InputBufferLength
0x14001416e  xor     r8d, r8d; InputBuffer
0x140014171  mov     [rsp+120h+var_100], rax; PVOID
0x140014176  mov     edx, 70048h; IoControlCode
0x14001417b  call    VmpSendDeviceControl
0x140014180  mov     r15d, eax
0x140014183  test    eax, eax
0x140014185  js      loc_140014214
0x14001418b  lea     rcx, [rbp+57h+var_D0]; this
0x14001418f  call    ?IsRecognized@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsRecognized(void)
0x140014194  test    al, al
0x140014196  jz      short loc_140014208
0x140014198  mov     rcx, [rsi+158h]; struct _DEVICE_OBJECT *
0x14001419f  lea     rdx, [rsp+120h+var_E8]; unsigned __int64 *
0x1400141a4  call    ?VmpDiskGetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@PEA_K@Z; VmpDiskGetGptAttributes(_DEVICE_OBJECT *,unsigned __int64 *)
0x1400141a9  mov     cl, [rdi+8]
0x1400141ac  mov     r15d, eax
0x1400141af  test    eax, eax
0x1400141b1  js      short loc_140014210
0x1400141b3  test    cl, cl
0x1400141b5  jz      short loc_1400141E0
0x1400141b7  mov     rax, [rsp+120h+var_E8]
0x1400141bc  lea     r9, [rsi+198h]; struct _GUID *
0x1400141c3  mov     qword ptr [rsp+120h+var_F8], rax; unsigned __int64
0x1400141c8  xor     r8d, r8d; struct _GUID *
0x1400141cb  mov     dl, 1; unsigned __int8
0x1400141cd  mov     dword ptr [rsp+120h+var_100], r13d; unsigned int
0x1400141d2  xor     ecx, ecx; unsigned __int8
0x1400141d4  call    ?VmpStoreGptAttributesRevertRecord@@YAJEEPEAU_GUID@@0K_K@Z; VmpStoreGptAttributesRevertRecord(uchar,uchar,_GUID *,_GUID *,ulong,unsigned __int64)
0x1400141d9  mov     r15d, eax
0x1400141dc  test    eax, eax
0x1400141de  js      short loc_140014214
0x1400141e0  mov     rdx, [rdi]; unsigned __int64
0x1400141e3  mov     rcx, [rsi+158h]; struct _DEVICE_OBJECT *
0x1400141ea  call    ?VmpDiskSetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@_KE@Z; VmpDiskSetGptAttributes(_DEVICE_OBJECT *,unsigned __int64,uchar)
0x1400141ef  mov     cl, [rdi+8]
0x1400141f2  mov     r15d, eax
0x1400141f5  test    eax, eax
0x1400141f7  js      short loc_140014210
0x1400141f9  test    cl, cl
0x1400141fb  jnz     short loc_140014208
0x1400141fd  mov     rdx, [rdi]; unsigned __int64
0x140014200  mov     rcx, rsi; struct VM_VOLUME_EXTENSION *
0x140014203  call    ?VmpApplyGptAttributes@@YAXPEAVVM_VOLUME_EXTENSION@@_K@Z; VmpApplyGptAttributes(VM_VOLUME_EXTENSION *,unsigned __int64)
0x140014208  mov     r14, [r14]
0x14001420b  jmp     loc_140014125
0x140014210  test    cl, cl
0x140014212  jmp     short loc_140014218
0x140014214  cmp     [rdi+8], r13b
0x140014218  jz      short loc_140014222
0x14001421a  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x14001421d  call    ?VmpRevertGptAttributes@@YAXPEAVVM_VOLUME_EXTENSION@@@Z; VmpRevertGptAttributes(VM_VOLUME_EXTENSION *)
0x140014222  mov     eax, r15d
0x140014225  jmp     loc_140014371
0x14001422a  test    eax, eax
0x14001422c  jnz     loc_140014365
0x140014232  cmp     [rdi+9], r12b
0x140014236  jz      loc_14001436C
0x14001423c  cmp     [rdi+8], r12b
0x140014240  jz      short loc_1400142A1
0x140014242  mov     rax, [r13+30h]
0x140014246  lea     rdx, [rsp+120h+var_F0]; unsigned int *
0x14001424b  mov     rsi, [rsp+120h+var_E8]
0x140014250  mov     rcx, [rbx+168h]; struct _DEVICE_OBJECT *
0x140014257  mov     [rbx+140h], rax
0x14001425e  mov     [rbx+148h], rsi
0x140014265  mov     al, [rdi+9]
0x140014268  mov     [rbx+150h], al
0x14001426e  call    ?VmpQueryDiskSignature@@YAJPEAU_DEVICE_OBJECT@@PEAK@Z; VmpQueryDiskSignature(_DEVICE_OBJECT *,ulong *)
0x140014273  test    eax, eax
0x140014275  js      loc_140013F52
0x14001427b  mov     r14d, [rsp+120h+var_F0]
0x140014280  xor     r9d, r9d; struct _GUID *
0x140014283  mov     qword ptr [rsp+120h+var_F8], rsi; unsigned __int64
0x140014288  xor     r8d, r8d; struct _GUID *
0x14001428b  xor     edx, edx; unsigned __int8
0x14001428d  mov     dword ptr [rsp+120h+var_100], r14d; unsigned int
0x140014292  xor     ecx, ecx; unsigned __int8
0x140014294  call    ?VmpStoreGptAttributesRevertRecord@@YAJEEPEAU_GUID@@0K_K@Z; VmpStoreGptAttributesRevertRecord(uchar,uchar,_GUID *,_GUID *,ulong,unsigned __int64)
0x140014299  test    eax, eax
0x14001429b  js      loc_140013F52
0x1400142a1  mov     rdx, [rdi]; unsigned __int64
0x1400142a4  mov     rcx, [rbx+158h]; struct _DEVICE_OBJECT *
0x1400142ab  call    ?VmpDiskSetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@_KE@Z; VmpDiskSetGptAttributes(_DEVICE_OBJECT *,unsigned __int64,uchar)
0x1400142b0  mov     cl, [rdi+8]
0x1400142b3  mov     esi, eax
0x1400142b5  test    eax, eax
0x1400142b7  jns     short loc_1400142D3
0x1400142b9  test    cl, cl
0x1400142bb  jz      loc_140013FA1
0x1400142c1  xor     r9d, r9d
0x1400142c4  mov     dword ptr [rsp+120h+var_100], r14d
0x1400142c9  xor     r8d, r8d
0x1400142cc  xor     edx, edx
0x1400142ce  jmp     loc_1400140F4
0x1400142d3  test    cl, cl
  ... truncated ...
```
