# VmpRevertGptAttributes(VM_VOLUME_EXTENSION *)

- ea: `0x140013ba0`
- end: `0x140013df7`
- name: `?VmpRevertGptAttributes@@YAXPEAVVM_VOLUME_EXTENSION@@@Z`
- size: `599`
- prototype: `void __fastcall(struct VM_VOLUME_EXTENSION *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x140002ba0`
- `0x140013e00`

## callees

- `0x140002db0`
- `0x1400031b0`
- `0x140005050`
- `0x140005090`
- `0x140005540`
- `0x140011bd8`
- `0x140011d94`
- `0x1400130b0`
- `0x140013ba0`

## pseudocode

```c
void __fastcall VmpRevertGptAttributes(struct VM_VOLUME_EXTENSION *a1)
{
  __int64 v1; // r14
  __int64 v3; // rdi
  bool v4; // zf
  __int64 v5; // rcx
  struct _DEVICE_OBJECT *v6; // rcx
  unsigned __int8 v7; // r8
  _QWORD **v8; // r14
  _QWORD *i; // rdi
  _QWORD *v10; // rsi
  unsigned __int8 v11; // r8
  unsigned int v12; // [rsp+30h] [rbp-79h] BYREF
  struct _GUID v13; // [rsp+38h] [rbp-71h] BYREF
  _DWORD v14[36]; // [rsp+50h] [rbp-59h] BYREF

  v1 = *((_QWORD *)a1 + 1);
  v3 = *(_QWORD *)(v1 + 392);
  v13 = 0;
  memset(v14, 0, sizeof(v14));
  v4 = *((_BYTE *)a1 + 426) == 0;
  v12 = 0;
  *((_QWORD *)a1 + 40) = 0;
  if ( v4 )
  {
    v6 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 43);
    if ( v6
      && VmpSendDeviceControl(v6, 0x70048u, 0, 0, v14, 0x90u) >= 0
      && SC_PART_ENTRY::IsRecognized((SC_PART_ENTRY *)v14) )
    {
      if ( v14[0] == 1 )
      {
        VmpDiskSetGptAttributes(*((struct _DEVICE_OBJECT **)a1 + 43), *((_QWORD *)a1 + 41), v7);
        VmpDeleteGptAttributesRevertRecord(0, 1, 0, (struct _GUID *)((char *)a1 + 408), 0);
        if ( *((_BYTE *)a1 + 336) )
        {
          v8 = (_QWORD **)(v1 + 208);
          for ( i = *v8; i != v8; i = (_QWORD *)*i )
          {
            v10 = i - 4;
            if ( i - 4 != (_QWORD *)a1
              && !*((_BYTE *)v10 + 426)
              && v10[45] == *((_QWORD *)a1 + 45)
              && VmpSendDeviceControl((PDEVICE_OBJECT)v10[43], 0x70048u, 0, 0, v14, 0x90u) >= 0
              && SC_PART_ENTRY::IsRecognized((SC_PART_ENTRY *)v14) )
            {
              VmpDiskSetGptAttributes((struct _DEVICE_OBJECT *)v10[43], *((_QWORD *)a1 + 41), v11);
              VmpDeleteGptAttributesRevertRecord(0, 1, 0, (struct _GUID *)(v10 + 51), 0);
            }
          }
        }
      }
      else if ( !v14[0] )
      {
        VmpDiskSetGptAttributes(*((struct _DEVICE_OBJECT **)a1 + 43), *((_QWORD *)a1 + 41), v7);
        if ( (int)VmpQueryDiskSignature(*((struct _DEVICE_OBJECT **)a1 + 45), &v12) >= 0 )
          VmpDeleteGptAttributesRevertRecord(0, 0, 0, 0, v12);
      }
    }
  }
  else
  {
    v5 = *((_QWORD *)a1 + 54);
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64, struct _GUID *))(v3 + 120))(v5, &v13);
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(v3 + 176))(*((_QWORD *)a1 + 54), *((_QWORD *)a1 + 41), 0);
      VmpDeleteGptAttributesRevertRecord(1, 0, &v13, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x140013ba0  mov     [rsp-8+arg_8], rbx
0x140013ba5  mov     [rsp-8+arg_10], rsi
0x140013baa  push    rbp
0x140013bab  push    rdi
0x140013bac  push    r14
0x140013bae  lea     rbp, [rsp-47h]
0x140013bb3  sub     rsp, 0F0h
0x140013bba  mov     rax, cs:__security_cookie
0x140013bc1  xor     rax, rsp
0x140013bc4  mov     [rbp+57h+var_20], rax
0x140013bc8  mov     r14, [rcx+8]
0x140013bcc  mov     rbx, rcx
0x140013bcf  xorps   xmm0, xmm0
0x140013bd2  lea     rcx, [rbp+57h+var_B0]; void *
0x140013bd6  xor     edx, edx; Val
0x140013bd8  mov     r8d, 90h; Size
0x140013bde  mov     rdi, [r14+188h]
0x140013be5  movups  xmmword ptr [rbp+57h+var_C8.Data1], xmm0
0x140013be9  call    memset
0x140013bee  cmp     byte ptr [rbx+1AAh], 0
0x140013bf5  mov     [rbp+57h+var_D0], 0
0x140013bfc  mov     qword ptr [rbx+140h], 0
0x140013c07  jz      short loc_140013C56
0x140013c09  mov     rcx, [rbx+1B0h]
0x140013c10  test    rcx, rcx
0x140013c13  jz      loc_140013DD2
0x140013c19  mov     rax, [rdi+78h]
0x140013c1d  lea     rdx, [rbp+57h+var_C8]
0x140013c21  call    _guard_dispatch_icall
0x140013c26  mov     rax, [rdi+0B0h]
0x140013c2d  xor     r8d, r8d
0x140013c30  mov     rdx, [rbx+148h]
0x140013c37  mov     rcx, [rbx+1B0h]
0x140013c3e  call    _guard_dispatch_icall
0x140013c43  lea     r8, [rbp+57h+var_C8]
0x140013c47  mov     dword ptr [rsp+100h+var_E0], 0
0x140013c4f  mov     cl, 1
0x140013c51  jmp     loc_140013DC8
0x140013c56  mov     rcx, [rbx+158h]; DeviceObject
0x140013c5d  test    rcx, rcx
0x140013c60  jz      loc_140013DD2
0x140013c66  lea     rax, [rbp+57h+var_B0]
0x140013c6a  mov     [rsp+100h+var_D8], 90h; ULONG
0x140013c72  xor     r9d, r9d; InputBufferLength
0x140013c75  mov     [rsp+100h+var_E0], rax; PVOID
0x140013c7a  xor     r8d, r8d; InputBuffer
0x140013c7d  mov     edx, 70048h; IoControlCode
0x140013c82  call    VmpSendDeviceControl
0x140013c87  test    eax, eax
0x140013c89  js      loc_140013DD2
0x140013c8f  lea     rcx, [rbp+57h+var_B0]; this
0x140013c93  call    ?IsRecognized@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsRecognized(void)
0x140013c98  test    al, al
0x140013c9a  jz      loc_140013DD2
0x140013ca0  mov     eax, [rbp+57h+var_B0]
0x140013ca3  cmp     eax, 1
0x140013ca6  jnz     loc_140013D91
0x140013cac  mov     rdx, [rbx+148h]; unsigned __int64
0x140013cb3  mov     rcx, [rbx+158h]; struct _DEVICE_OBJECT *
0x140013cba  call    ?VmpDiskSetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@_KE@Z; VmpDiskSetGptAttributes(_DEVICE_OBJECT *,unsigned __int64,uchar)
0x140013cbf  lea     r9, [rbx+198h]; struct _GUID *
0x140013cc6  mov     dword ptr [rsp+100h+var_E0], 0; unsigned int
0x140013cce  xor     r8d, r8d; struct _GUID *
0x140013cd1  mov     dl, 1; unsigned __int8
0x140013cd3  xor     ecx, ecx; unsigned __int8
0x140013cd5  call    ?VmpDeleteGptAttributesRevertRecord@@YAXEEPEAU_GUID@@0K@Z; VmpDeleteGptAttributesRevertRecord(uchar,uchar,_GUID *,_GUID *,ulong)
0x140013cda  cmp     byte ptr [rbx+150h], 0
0x140013ce1  jz      loc_140013DD2
0x140013ce7  add     r14, 0D0h
0x140013cee  mov     rdi, [r14]
0x140013cf1  jmp     loc_140013D86
0x140013cf6  lea     rsi, [rdi-20h]
0x140013cfa  cmp     rsi, rbx
0x140013cfd  jz      loc_140013D83
0x140013d03  cmp     byte ptr [rsi+1AAh], 0
0x140013d0a  jnz     short loc_140013D83
0x140013d0c  mov     rax, [rbx+168h]
0x140013d13  cmp     [rsi+168h], rax
0x140013d1a  jnz     short loc_140013D83
0x140013d1c  mov     rcx, [rsi+158h]; DeviceObject
0x140013d23  lea     rax, [rbp+57h+var_B0]
0x140013d27  mov     [rsp+100h+var_D8], 90h; ULONG
0x140013d2f  xor     r9d, r9d; InputBufferLength
0x140013d32  xor     r8d, r8d; InputBuffer
0x140013d35  mov     [rsp+100h+var_E0], rax; PVOID
0x140013d3a  mov     edx, 70048h; IoControlCode
0x140013d3f  call    VmpSendDeviceControl
0x140013d44  test    eax, eax
0x140013d46  js      short loc_140013D83
0x140013d48  lea     rcx, [rbp+57h+var_B0]; this
0x140013d4c  call    ?IsRecognized@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsRecognized(void)
0x140013d51  test    al, al
0x140013d53  jz      short loc_140013D83
0x140013d55  mov     rdx, [rbx+148h]; unsigned __int64
0x140013d5c  mov     rcx, [rsi+158h]; struct _DEVICE_OBJECT *
0x140013d63  call    ?VmpDiskSetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@_KE@Z; VmpDiskSetGptAttributes(_DEVICE_OBJECT *,unsigned __int64,uchar)
0x140013d68  lea     r9, [rsi+198h]; struct _GUID *
0x140013d6f  mov     dword ptr [rsp+100h+var_E0], 0; unsigned int
0x140013d77  xor     r8d, r8d; struct _GUID *
0x140013d7a  mov     dl, 1; unsigned __int8
0x140013d7c  xor     ecx, ecx; unsigned __int8
0x140013d7e  call    ?VmpDeleteGptAttributesRevertRecord@@YAXEEPEAU_GUID@@0K@Z; VmpDeleteGptAttributesRevertRecord(uchar,uchar,_GUID *,_GUID *,ulong)
0x140013d83  mov     rdi, [rdi]
0x140013d86  cmp     rdi, r14
0x140013d89  jnz     loc_140013CF6
0x140013d8f  jmp     short loc_140013DD2
0x140013d91  test    eax, eax
0x140013d93  jnz     short loc_140013DD2
0x140013d95  mov     rdx, [rbx+148h]; unsigned __int64
0x140013d9c  mov     rcx, [rbx+158h]; struct _DEVICE_OBJECT *
0x140013da3  call    ?VmpDiskSetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@_KE@Z; VmpDiskSetGptAttributes(_DEVICE_OBJECT *,unsigned __int64,uchar)
0x140013da8  mov     rcx, [rbx+168h]; struct _DEVICE_OBJECT *
0x140013daf  lea     rdx, [rbp+57h+var_D0]; unsigned int *
0x140013db3  call    ?VmpQueryDiskSignature@@YAJPEAU_DEVICE_OBJECT@@PEAK@Z; VmpQueryDiskSignature(_DEVICE_OBJECT *,ulong *)
0x140013db8  test    eax, eax
0x140013dba  js      short loc_140013DD2
0x140013dbc  mov     eax, [rbp+57h+var_D0]
0x140013dbf  xor     r8d, r8d; struct _GUID *
0x140013dc2  xor     ecx, ecx; unsigned __int8
0x140013dc4  mov     dword ptr [rsp+100h+var_E0], eax; unsigned int
0x140013dc8  xor     r9d, r9d; struct _GUID *
0x140013dcb  xor     edx, edx; unsigned __int8
0x140013dcd  call    ?VmpDeleteGptAttributesRevertRecord@@YAXEEPEAU_GUID@@0K@Z; VmpDeleteGptAttributesRevertRecord(uchar,uchar,_GUID *,_GUID *,ulong)
0x140013dd2  mov     rcx, [rbp+57h+var_20]
0x140013dd6  xor     rcx, rsp; StackCookie
0x140013dd9  call    __security_check_cookie
0x140013dde  lea     r11, [rsp+100h+var_10]
0x140013de6  mov     rbx, [r11+28h]
0x140013dea  mov     rsi, [r11+30h]
0x140013dee  mov     rsp, r11
0x140013df1  pop     r14
0x140013df3  pop     rdi
0x140013df4  pop     rbp
0x140013df5  retn
```
