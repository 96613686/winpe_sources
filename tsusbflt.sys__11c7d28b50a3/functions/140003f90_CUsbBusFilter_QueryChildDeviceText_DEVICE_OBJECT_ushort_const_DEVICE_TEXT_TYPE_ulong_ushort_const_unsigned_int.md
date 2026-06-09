# CUsbBusFilter::QueryChildDeviceText(_DEVICE_OBJECT *,ushort const *,DEVICE_TEXT_TYPE,ulong,ushort const * *,unsigned __int64 *)

- ea: `0x140003f90`
- end: `0x14000447a`
- name: `?QueryChildDeviceText@CUsbBusFilter@@AEAAJPEAU_DEVICE_OBJECT@@PEBGW4DEVICE_TEXT_TYPE@@KPEAPEBGPEA_K@Z`
- size: `1258`
- prototype: `__int64 __usercall@<rax>(CUsbBusFilter *__hidden this@<rcx>, struct _DEVICE_OBJECT *@<rdx>, const unsigned __int16 *@<r8>, enum DEVICE_TEXT_TYPE@<r9d>, unsigned int, const unsigned __int16 **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140001e80`
- `0x140004480`

## callees

- `0x140003f90`
- `0x140004724`
- `0x140004f48`
- `0x14000a2e8`
- `0x14000a9f0`
- `0x14000aa30`
- `0x14000ab00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004420`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004420`

## pseudocode

```c
__int64 __fastcall CUsbBusFilter::QueryChildDeviceText(
        CUsbBusFilter *this,
        struct _DEVICE_OBJECT *a2,
        const unsigned __int16 *a3,
        enum DEVICE_TEXT_TYPE a4,
        unsigned int a5,
        unsigned __int16 **a6,
        unsigned __int64 *a7)
{
  __int64 v10; // rdx
  unsigned __int16 *v11; // rdi
  int ProprietaryIdExtension; // ebx
  PDEVICE_OBJECT v13; // rcx
  unsigned __int16 v14; // dx
  int v15; // r9d
  __int64 v16; // rbx
  const wchar_t *v17; // rax
  NTSTATUS v18; // r9d
  size_t v19; // rcx
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  size_t pcchLength; // [rsp+40h] [rbp-C0h] BYREF
  enum DEVICE_TEXT_TYPE v24; // [rsp+48h] [rbp-B8h]
  __int128 v25; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v26; // [rsp+60h] [rbp-A0h]
  __int128 v27; // [rsp+70h] [rbp-90h]
  __int64 v28; // [rsp+80h] [rbp-80h]
  _QWORD v29[18]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v30; // [rsp+120h] [rbp+20h] BYREF
  _DWORD v31[18]; // [rsp+130h] [rbp+30h] BYREF

  v24 = a4;
  v28 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  memset(v29, 0, 0x88u);
  memset(v31, 0, sizeof(v31));
  v10 = *(_QWORD *)this;
  v21 = 0;
  v11 = 0;
  v22 = 0;
  pcchLength = 0;
  v30 = 0;
  ProprietaryIdExtension = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, _QWORD, unsigned __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[83].Blink)(
                             WPP_MAIN_CB.Queue.ListEntry.Blink,
                             v10,
                             0,
                             &v22);
  if ( ProprietaryIdExtension >= 0 )
  {
    if ( a3 )
    {
      ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[155].Flink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        *(_QWORD *)this);
      ProprietaryIdExtension = CUsbBusFilter::QueryProprietaryIdExtension(
                                 this,
                                 a3,
                                 (struct _PDO_PROPRIETARY_ID_EXTENSION **)&pcchLength);
      if ( ProprietaryIdExtension >= 0 )
      {
        v16 = *(_QWORD *)(pcchLength + 8);
        memset(v29, 0, 0x88u);
        v29[0] = 0x100000088LL;
        v29[4] = v16;
        ProprietaryIdExtension = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, unsigned __int64, _QWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[84].Flink)(
                                   WPP_MAIN_CB.Queue.ListEntry.Blink,
                                   v22,
                                   v29);
      }
      ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[155].Blink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        *(_QWORD *)this);
    }
    else
    {
      memset(v29, 0, 0x88u);
      v29[0] = 0x100000088LL;
      v29[4] = a2;
      ProprietaryIdExtension = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, unsigned __int64, _QWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[84].Flink)(
                                 WPP_MAIN_CB.Queue.ListEntry.Blink,
                                 v22,
                                 v29);
    }
    if ( ProprietaryIdExtension >= 0 )
    {
      *(_QWORD *)&v26 = 0;
      v28 = 0;
      v25 = 0;
      *((_QWORD *)&v26 + 1) = 0x100000001LL;
      LODWORD(v25) = 56;
      v27 = v22;
      ProprietaryIdExtension = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int128 *, unsigned __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[123].Blink)(
                                 WPP_MAIN_CB.Queue.ListEntry.Blink,
                                 &v25,
                                 v22,
                                 &v21);
      if ( ProprietaryIdExtension >= 0 )
      {
        *(_DWORD *)(((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[142].Blink)(
                      WPP_MAIN_CB.Queue.ListEntry.Blink,
                      v21)
                  + 48) = -1073741637;
        v31[2] = v24;
        v31[4] = a5;
        LOWORD(v31[0]) = 3099;
        ((void (__fastcall *)(struct _LIST_ENTRY *, __int64, _DWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Flink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          v21,
          v31);
        v30 = 0x200000010uLL;
        if ( ((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *, __int64, unsigned __int64, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Blink)(
               WPP_MAIN_CB.Queue.ListEntry.Blink,
               v21,
               v22,
               &v30) )
        {
          ProprietaryIdExtension = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[127].Flink)(
                                     WPP_MAIN_CB.Queue.ListEntry.Blink,
                                     v21);
          if ( ProprietaryIdExtension >= 0 )
          {
            v17 = (const wchar_t *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[138].Flink)(
                                     WPP_MAIN_CB.Queue.ListEntry.Blink,
                                     v21);
            pcchLength = 0;
            v11 = (unsigned __int16 *)v17;
            if ( v17 )
            {
              v18 = RtlStringLengthWorkerW(v17, 0x7FFFu, &pcchLength);
              if ( v18 >= 0 )
              {
                v19 = pcchLength;
                *a6 = v11;
                v11 = 0;
                *a7 = 2 * v19;
                ProprietaryIdExtension = 0;
                goto LABEL_36;
              }
            }
            else
            {
              v18 = -1073741811;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_d(
                (__int64)WPP_GLOBAL_Control->AttachedDevice,
                0x39u,
                (__int64)WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids,
                v18);
            ProprietaryIdExtension = -1073741808;
          }
          else
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v14 = 56;
              goto LABEL_5;
            }
          }
        }
        else
        {
          ProprietaryIdExtension = -2147483631;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v14 = 55;
            v15 = -2147483631;
            goto LABEL_6;
          }
        }
      }
      else
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v14 = 54;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v14 = 53;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v14 = 52;
LABEL_5:
      v15 = ProprietaryIdExtension;
LABEL_6:
      WPP_SF_d((__int64)v13->AttachedDevice, v14, (__int64)WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids, v15);
    }
  }
LABEL_36:
  if ( v21 )
    ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  if ( v22 )
    ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
  return (unsigned int)ProprietaryIdExtension;
}

```

## disassembly

```asm
0x140003f90  mov     [rsp-8+arg_8], rbx
0x140003f95  push    rbp
0x140003f96  push    rsi
0x140003f97  push    rdi
0x140003f98  push    r12
0x140003f9a  push    r13
0x140003f9c  push    r14
0x140003f9e  push    r15
0x140003fa0  lea     rbp, [rsp-80h]
0x140003fa5  sub     rsp, 180h
0x140003fac  mov     rax, cs:__security_cookie
0x140003fb3  xor     rax, rsp
0x140003fb6  mov     [rbp+0B0h+var_38], rax
0x140003fba  mov     r12, [rbp+0B0h+arg_28]
0x140003fc1  xorps   xmm0, xmm0
0x140003fc4  mov     r13, [rbp+0B0h+arg_30]
0x140003fcb  mov     rsi, r8
0x140003fce  mov     r15, rdx
0x140003fd1  mov     [rsp+1B0h+var_168], r9d
0x140003fd6  mov     r14, rcx
0x140003fd9  xor     eax, eax
0x140003fdb  xor     edx, edx; Val
0x140003fdd  mov     [rbp+0B0h+var_130], rax
0x140003fe1  mov     r8d, 88h; Size
0x140003fe7  lea     rcx, [rbp+0B0h+var_120]; void *
0x140003feb  movups  [rsp+1B0h+var_160], xmm0
0x140003ff0  movups  [rsp+1B0h+var_150], xmm0
0x140003ff5  movups  [rsp+1B0h+var_140], xmm0
0x140003ffa  call    memset
0x140003fff  xor     edx, edx; Val
0x140004001  lea     rcx, [rbp+0B0h+var_80]; void *
0x140004005  lea     r8d, [rdx+48h]; Size
0x140004009  call    memset
0x14000400e  mov     rdx, [r14]
0x140004011  lea     r9, [rsp+1B0h+var_178]
0x140004016  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000401d  xor     eax, eax
0x14000401f  mov     [rsp+1B0h+var_180], rax
0x140004024  mov     edi, eax
0x140004026  mov     [rsp+1B0h+var_178], rax
0x14000402b  xorps   xmm0, xmm0
0x14000402e  mov     [rsp+1B0h+pcchLength], rax
0x140004033  xor     r8d, r8d
0x140004036  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000403d  movups  [rbp+0B0h+var_90], xmm0
0x140004041  mov     rax, [rax+538h]
0x140004048  call    _guard_dispatch_icall
0x14000404d  mov     ebx, eax
0x14000404f  test    eax, eax
0x140004051  jns     short loc_14000408F
0x140004053  mov     rcx, cs:WPP_GLOBAL_Control
0x14000405a  lea     rax, WPP_GLOBAL_Control
0x140004061  cmp     rcx, rax
0x140004064  jz      loc_1400043F2
0x14000406a  cmp     byte ptr [rcx+29h], 2
0x14000406e  jb      loc_1400043F2
0x140004074  lea     edx, [rdi+34h]
0x140004077  mov     r9d, ebx
0x14000407a  mov     rcx, [rcx+18h]
0x14000407e  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140004085  call    WPP_SF_d
0x14000408a  jmp     loc_1400043F2
0x14000408f  test    rsi, rsi
0x140004092  jz      loc_14000413C
0x140004098  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000409f  mov     rdx, [r14]
0x1400040a2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400040a9  mov     rax, [rax+9B0h]
0x1400040b0  call    _guard_dispatch_icall
0x1400040b5  lea     r8, [rsp+1B0h+pcchLength]; struct _PDO_PROPRIETARY_ID_EXTENSION **
0x1400040ba  mov     rdx, rsi; unsigned __int16 *
0x1400040bd  mov     rcx, r14; this
0x1400040c0  call    ?QueryProprietaryIdExtension@CUsbBusFilter@@AEAAJPEBGPEAPEAU_PDO_PROPRIETARY_ID_EXTENSION@@@Z; CUsbBusFilter::QueryProprietaryIdExtension(ushort const *,_PDO_PROPRIETARY_ID_EXTENSION * *)
0x1400040c5  mov     ebx, eax
0x1400040c7  mov     esi, 1
0x1400040cc  test    eax, eax
0x1400040ce  js      short loc_14000411D
0x1400040d0  mov     rax, [rsp+1B0h+pcchLength]
0x1400040d5  lea     rcx, [rbp+0B0h+var_120]; void *
0x1400040d9  mov     r15d, 88h
0x1400040df  xor     edx, edx; Val
0x1400040e1  mov     r8d, r15d; Size
0x1400040e4  mov     rbx, [rax+8]
0x1400040e8  call    memset
0x1400040ed  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400040f4  lea     r8, [rbp+0B0h+var_120]
0x1400040f8  mov     rdx, [rsp+1B0h+var_178]
0x1400040fd  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140004104  mov     [rbp+0B0h+var_120], r15d
0x140004108  mov     [rbp+0B0h+var_11C], esi
0x14000410b  mov     [rbp+0B0h+var_100], rbx
0x14000410f  mov     rax, [rax+540h]
0x140004116  call    _guard_dispatch_icall
0x14000411b  mov     ebx, eax
0x14000411d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140004124  mov     rdx, [r14]
0x140004127  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000412e  mov     rax, [rax+9B8h]
0x140004135  call    _guard_dispatch_icall
0x14000413a  jmp     short loc_140004183
0x14000413c  mov     ebx, 88h
0x140004141  lea     rcx, [rbp+0B0h+var_120]; void *
0x140004145  mov     r8d, ebx; Size
0x140004148  xor     edx, edx; Val
0x14000414a  call    memset
0x14000414f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140004156  lea     r8, [rbp+0B0h+var_120]
0x14000415a  mov     rdx, [rsp+1B0h+var_178]
0x14000415f  mov     esi, 1
0x140004164  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000416b  mov     [rbp+0B0h+var_120], ebx
0x14000416e  mov     [rbp+0B0h+var_11C], esi
0x140004171  mov     [rbp+0B0h+var_100], r15
0x140004175  mov     rax, [rax+540h]
0x14000417c  call    _guard_dispatch_icall
0x140004181  mov     ebx, eax
0x140004183  test    ebx, ebx
0x140004185  jns     short loc_1400041B2
0x140004187  mov     rcx, cs:WPP_GLOBAL_Control
0x14000418e  lea     rax, WPP_GLOBAL_Control
0x140004195  cmp     rcx, rax
0x140004198  jz      loc_1400043F2
0x14000419e  cmp     byte ptr [rcx+29h], 2
0x1400041a2  jb      loc_1400043F2
0x1400041a8  mov     edx, 35h ; '5'
0x1400041ad  jmp     loc_140004077
0x1400041b2  mov     r8, [rsp+1B0h+var_178]
0x1400041b7  lea     r9, [rsp+1B0h+var_180]
0x1400041bc  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400041c3  lea     rdx, [rsp+1B0h+var_160]
0x1400041c8  xor     eax, eax
0x1400041ca  xorps   xmm0, xmm0
0x1400041cd  movups  [rsp+1B0h+var_150], xmm0
0x1400041d2  mov     [rbp+0B0h+var_130], rax
0x1400041d6  movups  [rsp+1B0h+var_160], xmm0
0x1400041db  lea     r14d, [rax+38h]
0x1400041df  mov     dword ptr [rsp+1B0h+var_150+8], esi
0x1400041e3  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400041ea  movups  [rsp+1B0h+var_140], xmm0
0x1400041ef  mov     dword ptr [rsp+1B0h+var_160], r14d
0x1400041f4  mov     dword ptr [rsp+1B0h+var_150+0Ch], esi
0x1400041f8  mov     qword ptr [rsp+1B0h+var_140], r8
0x1400041fd  mov     rax, [rax+7B8h]
0x140004204  call    _guard_dispatch_icall
0x140004209  mov     ebx, eax
0x14000420b  test    eax, eax
0x14000420d  jns     short loc_140004239
0x14000420f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004216  lea     rax, WPP_GLOBAL_Control
0x14000421d  cmp     rcx, rax
0x140004220  jz      loc_1400043F2
0x140004226  cmp     byte ptr [rcx+29h], 2
0x14000422a  jb      loc_1400043F2
0x140004230  lea     edx, [r14-2]
0x140004234  jmp     loc_140004077
0x140004239  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140004240  mov     rdx, [rsp+1B0h+var_180]
0x140004245  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000424c  mov     rax, [rax+8E8h]
0x140004253  call    _guard_dispatch_icall
0x140004258  lea     r8, [rbp+0B0h+var_80]
0x14000425c  mov     dword ptr [rax+30h], 0C00000BBh
0x140004263  mov     eax, [rsp+1B0h+var_168]
0x140004267  mov     rdx, [rsp+1B0h+var_180]
0x14000426c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140004273  mov     [rbp+0B0h+var_78], eax
0x140004276  mov     eax, [rbp+0B0h+arg_20]
0x14000427c  mov     [rbp+0B0h+var_70], eax
0x14000427f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140004286  mov     [rbp+0B0h+var_80], 0C1Bh
0x14000428c  mov     rax, [rax+7E0h]
0x140004293  call    _guard_dispatch_icall
0x140004298  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000429f  lea     r9, [rbp+0B0h+var_90]
0x1400042a3  mov     r8, [rsp+1B0h+var_178]
0x1400042a8  mov     rdx, [rsp+1B0h+var_180]
0x1400042ad  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400042b4  mov     qword ptr [rbp+0B0h+var_90+8], rdi
0x1400042b8  mov     dword ptr [rbp+0B0h+var_90], 10h
0x1400042bf  mov     dword ptr [rbp+0B0h+var_90+4], 2
0x1400042c6  mov     rax, [rax+7E8h]
0x1400042cd  call    _guard_dispatch_icall
0x1400042d2  test    al, al
0x1400042d4  jnz     short loc_14000430C
0x1400042d6  mov     ebx, 80000011h
0x1400042db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042e2  lea     rax, WPP_GLOBAL_Control
0x1400042e9  cmp     rcx, rax
0x1400042ec  jz      loc_1400043F2
0x1400042f2  cmp     byte ptr [rcx+29h], 2
0x1400042f6  jb      loc_1400043F2
0x1400042fc  mov     edx, 37h ; '7'
0x140004301  mov     r9d, 80000011h
0x140004307  jmp     loc_14000407A
0x14000430c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140004313  mov     rdx, [rsp+1B0h+var_180]
0x140004318  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000431f  mov     rax, [rax+7F0h]
0x140004326  call    _guard_dispatch_icall
0x14000432b  mov     ebx, eax
0x14000432d  test    eax, eax
0x14000432f  jns     short loc_14000435A
0x140004331  mov     rcx, cs:WPP_GLOBAL_Control
0x140004338  lea     rax, WPP_GLOBAL_Control
0x14000433f  cmp     rcx, rax
0x140004342  jz      loc_1400043F2
0x140004348  cmp     byte ptr [rcx+29h], 2
0x14000434c  jb      loc_1400043F2
0x140004352  mov     edx, r14d
0x140004355  jmp     loc_140004077
0x14000435a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140004361  mov     rdx, [rsp+1B0h+var_180]
0x140004366  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000436d  mov     rax, [rax+8A0h]
0x140004374  call    _guard_dispatch_icall
0x140004379  mov     [rsp+1B0h+pcchLength], 0
0x140004382  mov     rdi, rax
0x140004385  test    rax, rax
0x140004388  jz      short loc_1400043B9
0x14000438a  lea     r8, [rsp+1B0h+pcchLength]; pcchLength
0x14000438f  mov     edx, 7FFFh; cchMax
0x140004394  mov     rcx, rax; psz
0x140004397  call    RtlStringLengthWorkerW
0x14000439c  mov     r9d, eax
0x14000439f  test    eax, eax
0x1400043a1  js      short loc_1400043BF
0x1400043a3  mov     rcx, [rsp+1B0h+pcchLength]
0x1400043a8  mov     [r12], rdi
0x1400043ac  add     rcx, rcx
0x1400043af  xor     edi, edi
0x1400043b1  mov     [r13+0], rcx
0x1400043b5  xor     ebx, ebx
0x1400043b7  jmp     short loc_1400043F2
0x1400043b9  mov     r9d, 0C000000Dh
0x1400043bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400043c6  lea     rax, WPP_GLOBAL_Control
0x1400043cd  cmp     rcx, rax
0x1400043d0  jz      short loc_1400043ED
0x1400043d2  cmp     byte ptr [rcx+29h], 2
0x1400043d6  jb      short loc_1400043ED
0x1400043d8  mov     rcx, [rcx+18h]
0x1400043dc  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x1400043e3  mov     edx, 39h ; '9'
0x1400043e8  call    WPP_SF_d
0x1400043ed  mov     ebx, 0C0000010h
0x1400043f2  mov     rdx, [rsp+1B0h+var_180]
0x1400043f7  test    rdx, rdx
0x1400043fa  jz      short loc_140004416
0x1400043fc  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140004403  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000440a  mov     rax, [rax+680h]
0x140004411  call    _guard_dispatch_icall
0x140004416  test    rdi, rdi
0x140004419  jz      short loc_14000442C
0x14000441b  xor     edx, edx; Tag
0x14000441d  mov     rcx, rdi; P
0x140004420  call    cs:__imp_ExFreePoolWithTag
0x140004427  nop     dword ptr [rax+rax+00h]
0x14000442c  mov     rdx, [rsp+1B0h+var_178]
0x140004431  test    rdx, rdx
0x140004434  jz      short loc_140004450
0x140004436  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000443d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140004444  mov     rax, [rax+680h]
0x14000444b  call    _guard_dispatch_icall
0x140004450  mov     eax, ebx
0x140004452  mov     rcx, [rbp+0B0h+var_38]
0x140004456  xor     rcx, rsp; StackCookie
0x140004459  call    __security_check_cookie
0x14000445e  mov     rbx, [rsp+1B0h+arg_8]
0x140004466  add     rsp, 180h
0x14000446d  pop     r15
0x14000446f  pop     r14
0x140004471  pop     r13
0x140004473  pop     r12
0x140004475  pop     rdi
0x140004476  pop     rsi
0x140004477  pop     rbp
0x140004478  retn
```
