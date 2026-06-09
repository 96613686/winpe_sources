# WcCopyFileMetaData

- ea: `0x14001e374`
- end: `0x14001e4f0`
- name: `WcCopyFileMetaData`
- size: `380`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x140017f64`
- `0x14001d8dc`

## callees

- `0x1400020c4`
- `0x140004198`
- `0x14001e028`
- `0x14001e374`
- `0x14002fb20`

## pseudocode

```c
__int64 __fastcall WcCopyFileMetaData(
        void *a1,
        struct _FILE_OBJECT *a2,
        struct _FLT_INSTANCE *a3,
        void *a4,
        struct _FILE_OBJECT *a5,
        struct _FLT_INSTANCE *a6,
        int a7)
{
  struct _FILE_OBJECT *v8; // r15
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // edx
  int v12; // r9d
  int v13; // eax
  char v15; // [rsp+30h] [rbp-48h]
  int v16; // [rsp+38h] [rbp-40h]

  v8 = a2;
  if ( a7 && a1 && a4 && a5 && a6 )
  {
    v9 = 0;
    if ( (a7 & 3) != 0 && (v10 = WcCopyFileDataStreams(a1, a2, a3, a4, a5, a6, a7), v9 = v10, v10 < 0) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v16 = v10;
        v12 = 109;
        v15 = -65;
LABEL_10:
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          15,
          v12,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          v15,
          v16);
      }
    }
    else if ( (a7 & 0xC) != 0 )
    {
      v13 = WcCopyFileBasicInformation(v8, a3, a5, a6, a7);
      v9 = v13;
      if ( v13 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v16 = v13;
        v12 = 110;
        v15 = -49;
        goto LABEL_10;
      }
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        15,
        108,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        172);
    }
    return (unsigned int)-1073741811;
  }
  return v9;
}

```

## disassembly

```asm
0x14001e374  push    rbx
0x14001e376  push    rbp
0x14001e377  push    rsi
0x14001e378  push    rdi
0x14001e379  push    r14
0x14001e37b  push    r15
0x14001e37d  sub     rsp, 48h
0x14001e381  mov     edi, [rsp+78h+arg_30]
0x14001e388  mov     r14, r8
0x14001e38b  mov     r15, rdx
0x14001e38e  test    edi, edi
0x14001e390  jz      loc_14001E48F
0x14001e396  test    rcx, rcx
0x14001e399  jz      loc_14001E48F
0x14001e39f  test    r9, r9
0x14001e3a2  jz      loc_14001E48F
0x14001e3a8  mov     rsi, [rsp+78h+arg_20]
0x14001e3b0  test    rsi, rsi
0x14001e3b3  jz      loc_14001E48F
0x14001e3b9  mov     rbp, [rsp+78h+arg_28]
0x14001e3c1  test    rbp, rbp
0x14001e3c4  jz      loc_14001E48F
0x14001e3ca  xor     ebx, ebx
0x14001e3cc  test    dil, 3
0x14001e3d0  jz      short loc_14001E446
0x14001e3d2  mov     dword ptr [rsp+78h+var_48], edi
0x14001e3d6  mov     [rsp+78h+var_50], rbp
0x14001e3db  mov     qword ptr [rsp+78h+var_58], rsi
0x14001e3e0  call    WcCopyFileDataStreams
0x14001e3e5  mov     ebx, eax
0x14001e3e7  test    eax, eax
0x14001e3e9  jns     short loc_14001E446
0x14001e3eb  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001e3f2  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001e3f9  jz      loc_14001E4E0
0x14001e3ff  mov     [rsp+78h+var_40], eax
0x14001e403  mov     r9d, 6Dh ; 'm'
0x14001e409  mov     dword ptr [rsp+78h+var_48], 0DBFh
0x14001e411  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e418  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001e41f  mov     [rsp+78h+var_50], rax
0x14001e424  mov     r8d, 0Fh
0x14001e42a  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001e431  mov     dl, 2
0x14001e433  mov     qword ptr [rsp+78h+var_58], rax
0x14001e438  mov     rcx, [rcx+40h]
0x14001e43c  call    WPP_RECORDER_SF_sDd
0x14001e441  jmp     loc_14001E4E0
0x14001e446  test    dil, 0Ch
0x14001e44a  jz      loc_14001E4E0
0x14001e450  mov     r9, rbp; PFLT_INSTANCE
0x14001e453  mov     [rsp+78h+var_58], edi; int
0x14001e457  mov     r8, rsi; PFILE_OBJECT
0x14001e45a  mov     rdx, r14; Instance
0x14001e45d  mov     rcx, r15; FileObject
0x14001e460  call    WcCopyFileBasicInformation
0x14001e465  mov     ebx, eax
0x14001e467  test    eax, eax
0x14001e469  jns     short loc_14001E4E0
0x14001e46b  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001e472  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001e479  jz      short loc_14001E4E0
0x14001e47b  mov     [rsp+78h+var_40], eax
0x14001e47f  mov     r9d, 6Eh ; 'n'
0x14001e485  mov     dword ptr [rsp+78h+var_48], 0DCFh
0x14001e48d  jmp     short loc_14001E411
0x14001e48f  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001e496  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001e49d  jz      short loc_14001E4DB
0x14001e49f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e4a6  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001e4ad  mov     r9d, 6Ch ; 'l'
0x14001e4b3  mov     dword ptr [rsp+78h+var_48], 0DACh
0x14001e4bb  mov     [rsp+78h+var_50], rax
0x14001e4c0  mov     dl, 2
0x14001e4c2  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001e4c9  mov     rcx, [rcx+40h]
0x14001e4cd  lea     r8d, [r9-5Dh]
0x14001e4d1  mov     qword ptr [rsp+78h+var_58], rax
0x14001e4d6  call    WPP_RECORDER_SF_sD
0x14001e4db  mov     ebx, 0C000000Dh
0x14001e4e0  mov     eax, ebx
0x14001e4e2  add     rsp, 48h
0x14001e4e6  pop     r15
0x14001e4e8  pop     r14
0x14001e4ea  pop     rdi
0x14001e4eb  pop     rsi
0x14001e4ec  pop     rbp
0x14001e4ed  pop     rbx
0x14001e4ee  retn
```
