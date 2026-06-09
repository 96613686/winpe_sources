# CUsbBusFilter::EvtIoInternalDeviceControl(WDFREQUEST__ *,unsigned __int64,ulong)

- ea: `0x140002bc4`
- end: `0x1400031a8`
- name: `?EvtIoInternalDeviceControl@CUsbBusFilter@@QEAAXPEAUWDFREQUEST__@@_KK@Z`
- size: `1508`
- prototype: `void __fastcall(CUsbBusFilter *__hidden this, struct WDFREQUEST__ *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140012540`

## callees

- `0x140002bc4`
- `0x140004480`
- `0x140004724`
- `0x140004f48`
- `0x14000a2e8`
- `0x14000a9f0`
- `0x14000aa30`
- `0x14000b140`

## pseudocode

```c
void __fastcall CUsbBusFilter::EvtIoInternalDeviceControl(
        CUsbBusFilter *this,
        struct WDFREQUEST__ *a2,
        unsigned __int64 a3,
        unsigned int a4)
{
  __int64 v7; // r8
  NTSTATUS v8; // ebx
  unsigned __int64 v9; // rdi
  unsigned int v10; // r9d
  unsigned int v11; // r9d
  unsigned int v12; // r9d
  unsigned int v13; // r9d
  PDEVICE_OBJECT v14; // rcx
  unsigned __int16 v15; // dx
  unsigned int v16; // r14d
  unsigned int v17; // ebx
  __int64 v18; // r12
  __int64 v19; // rax
  STRSAFE_PCNZWCH v20; // rcx
  int v21; // r8d
  int v22; // edx
  struct _LIST_ENTRY *Blink; // rax
  __int64 v24; // r9
  const wchar_t *v25; // r14
  size_t v26; // rdx
  void *v27; // [rsp+30h] [rbp-50h] BYREF
  STRSAFE_PCNZWCH psz; // [rsp+38h] [rbp-48h] BYREF
  size_t pcchLength; // [rsp+40h] [rbp-40h] BYREF
  _DWORD *v30; // [rsp+48h] [rbp-38h] BYREF
  struct _PDO_PROPRIETARY_ID_EXTENSION *v31; // [rsp+50h] [rbp-30h] BYREF
  size_t v32; // [rsp+58h] [rbp-28h] BYREF
  __int128 v33; // [rsp+60h] [rbp-20h] BYREF

  v33 = 0;
  if ( a4 >= 0x220448 )
  {
    v9 = 0;
    v10 = a4 - 2229323;
    if ( v10 )
    {
      v11 = v10 - 4;
      if ( v11 )
      {
        v12 = v11 - 16313;
        if ( v12 )
        {
          v13 = v12 - 12;
          if ( v13 )
          {
            if ( v13 == 4 )
            {
              CUsbBusFilter::QueryDeviceText(this, a2, a3);
              return;
            }
            goto LABEL_2;
          }
          psz = 0;
          v27 = 0;
          v30 = 0;
          v31 = 0;
          v8 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, STRSAFE_PCNZWCH *, void **))WPP_MAIN_CB.Queue.ListEntry.Flink[134].Blink)(
                 WPP_MAIN_CB.Queue.ListEntry.Blink,
                 a2,
                 2,
                 &psz,
                 &v27);
          if ( v8 < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              goto LABEL_4;
            v15 = 31;
            goto LABEL_16;
          }
          pcchLength = 0;
          if ( psz && (unsigned __int64)v27 >> 1 <= 0x7FFFFFFF )
          {
            v8 = RtlStringLengthWorkerW(psz, (unsigned __int64)v27 >> 1, &pcchLength);
            if ( v8 >= 0 )
            {
              v27 = (void *)(2 * pcchLength);
              v8 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, _DWORD **, struct _PDO_PROPRIETARY_ID_EXTENSION **))WPP_MAIN_CB.Queue.ListEntry.Flink[135].Flink)(
                     WPP_MAIN_CB.Queue.ListEntry.Blink,
                     a2,
                     4,
                     &v30,
                     &v31);
              if ( v8 < 0 )
              {
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                  goto LABEL_4;
                v15 = 33;
                goto LABEL_16;
              }
              ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[155].Flink)(
                WPP_MAIN_CB.Queue.ListEntry.Blink,
                *(_QWORD *)this);
              v16 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Flink)(
                      WPP_MAIN_CB.Queue.ListEntry.Blink,
                      *((_QWORD *)this + 3));
              v17 = 0;
              if ( v16 )
              {
                while ( 1 )
                {
                  v18 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[9].Flink)(
                          WPP_MAIN_CB.Queue.ListEntry.Blink,
                          *((_QWORD *)this + 3),
                          v17);
                  v19 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                          WPP_MAIN_CB.Queue.ListEntry.Blink,
                          v18,
                          off_14000F150);
                  v20 = psz;
                  do
                  {
                    v21 = *(STRSAFE_PCNZWCH)((char *)v20 + v19 + *(_QWORD *)(v19 + 96) + 104LL - (_QWORD)psz);
                    v22 = *v20 - v21;
                    if ( v22 )
                      break;
                    ++v20;
                  }
                  while ( v21 );
                  if ( !v22 )
                    break;
                  if ( ++v17 >= v16 )
                    goto LABEL_30;
                }
                if ( v18 )
                {
                  v9 = 4;
                  *v30 = *(_DWORD *)(v19 + 24);
LABEL_61:
                  v8 = 0;
                  goto LABEL_62;
                }
              }
LABEL_30:
              v8 = -1073741275;
              goto LABEL_62;
            }
          }
          else
          {
            v8 = -1073741811;
          }
          v27 = 0;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            goto LABEL_4;
          v15 = 32;
        }
        else
        {
          v30 = 0;
          pcchLength = 0;
          v27 = 0;
          psz = 0;
          Blink = WPP_MAIN_CB.Queue.ListEntry.Flink[134].Blink;
          v31 = 0;
          v8 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, _DWORD **, size_t *))Blink)(
                 WPP_MAIN_CB.Queue.ListEntry.Blink,
                 a2,
                 8,
                 &v30,
                 &pcchLength);
          if ( v8 < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              goto LABEL_4;
            v15 = 26;
            goto LABEL_16;
          }
          if ( a3 )
          {
            v8 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, void **, STRSAFE_PCNZWCH *))WPP_MAIN_CB.Queue.ListEntry.Flink[135].Flink)(
                   WPP_MAIN_CB.Queue.ListEntry.Blink,
                   a2,
                   2,
                   &v27,
                   &psz);
            if ( v8 < 0 )
            {
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                goto LABEL_4;
              v15 = 27;
              goto LABEL_16;
            }
          }
          else
          {
            v27 = 0;
            psz = 0;
          }
          v24 = (unsigned int)v30[1];
          if ( (unsigned int)(v24 + 8) <= pcchLength )
          {
            v25 = (const wchar_t *)((char *)v30 + v24 + 8);
            if ( v25 && (v26 = (pcchLength - v24 - 8) >> 1, v26 <= 0x7FFFFFFF) )
            {
              v8 = RtlStringLengthWorkerW(v25, v26, &v32);
              if ( v8 >= 0 )
              {
                ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[155].Flink)(
                  WPP_MAIN_CB.Queue.ListEntry.Blink,
                  *(_QWORD *)this);
                v8 = CUsbBusFilter::QueryProprietaryIdExtension(this, v25, &v31);
                if ( v8 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    WPP_SF_d(
                      (__int64)WPP_GLOBAL_Control->AttachedDevice,
                      0x1Eu,
                      (__int64)WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids,
                      v8);
                  }
                  goto LABEL_62;
                }
                v9 = *((_QWORD *)v31 + 10);
                if ( v9 <= (unsigned __int64)psz )
                {
                  memmove(v27, (char *)v31 + *((unsigned int *)v31 + 22) + 104, *((_QWORD *)v31 + 10));
                  goto LABEL_61;
                }
                v8 = -2147483643;
LABEL_62:
                ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[155].Blink)(
                  WPP_MAIN_CB.Queue.ListEntry.Blink,
                  *(_QWORD *)this);
                goto LABEL_4;
              }
            }
            else
            {
              v8 = -1073741811;
            }
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              goto LABEL_4;
            v15 = 29;
          }
          else
          {
            v8 = -1073741811;
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              goto LABEL_4;
            v15 = 28;
          }
        }
LABEL_16:
        WPP_SF_d((__int64)v14->AttachedDevice, v15, (__int64)WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids, v8);
        goto LABEL_4;
      }
    }
  }
LABEL_2:
  v7 = *((_QWORD *)this + 1);
  *(_QWORD *)&v33 = 0x800000010LL;
  if ( ((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2,
         v7,
         &v33) )
  {
    return;
  }
  v8 = -1073741808;
  v9 = 0;
LABEL_4:
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, unsigned __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[132].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    (unsigned int)v8,
    v9);
}

```

## disassembly

```asm
0x140002bc4  mov     [rsp-38h+arg_10], rbx
0x140002bc9  push    rbp
0x140002bca  push    rsi
0x140002bcb  push    rdi
0x140002bcc  push    r12
0x140002bce  push    r13
0x140002bd0  push    r14
0x140002bd2  push    r15
0x140002bd4  mov     rbp, rsp
0x140002bd7  sub     rsp, 80h
0x140002bde  mov     rax, cs:__security_cookie
0x140002be5  xor     rax, rsp
0x140002be8  mov     [rbp+var_10], rax
0x140002bec  xor     r13d, r13d
0x140002bef  mov     eax, 220428h
0x140002bf4  xorps   xmm0, xmm0
0x140002bf7  mov     r14, r8
0x140002bfa  mov     r15, rdx
0x140002bfd  mov     rsi, rcx
0x140002c00  movups  [rbp+var_20], xmm0
0x140002c04  cmp     r9d, eax
0x140002c07  ja      short loc_140002C3B
0x140002c09  jz      short loc_140002C64
0x140002c0b  mov     eax, 22001Fh
0x140002c10  cmp     r9d, eax
0x140002c13  ja      short loc_140002C2C
0x140002c15  jz      short loc_140002C64
0x140002c17  sub     r9d, 220003h
0x140002c1e  jz      short loc_140002C64
0x140002c20  sub     r9d, 4
0x140002c24  jz      short loc_140002C64
0x140002c26  sub     r9d, 8
0x140002c2a  jmp     short loc_140002C5E
0x140002c2c  sub     r9d, 220020h
0x140002c33  jz      short loc_140002C64
0x140002c35  sub     r9d, 7
0x140002c39  jmp     short loc_140002C5E
0x140002c3b  mov     eax, 220447h
0x140002c40  cmp     r9d, eax
0x140002c43  ja      loc_140002CEB
0x140002c49  jz      short loc_140002C64
0x140002c4b  sub     r9d, 22042Ch
0x140002c52  jz      short loc_140002C64
0x140002c54  sub     r9d, 7
0x140002c58  jz      short loc_140002C64
0x140002c5a  sub     r9d, 4
0x140002c5e  jz      short loc_140002C64
0x140002c60  sub     r9d, 4
0x140002c64  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002c6b  lea     r9, [rbp+var_20]
0x140002c6f  mov     r8, [rcx+8]
0x140002c73  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002c7a  mov     dword ptr [rbp+var_20], 10h
0x140002c81  mov     dword ptr [rbp+var_20+4], 8
0x140002c88  mov     rax, [rax+7E8h]
0x140002c8f  call    _guard_dispatch_icall
0x140002c94  test    al, al
0x140002c96  jnz     short loc_140002CC3
0x140002c98  mov     ebx, 0C0000010h
0x140002c9d  mov     rdi, r13
0x140002ca0  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002ca7  mov     r9, rdi
0x140002caa  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002cb1  mov     r8d, ebx
0x140002cb4  mov     rdx, r15
0x140002cb7  mov     rax, [rax+848h]
0x140002cbe  call    _guard_dispatch_icall
0x140002cc3  mov     rcx, [rbp+var_10]
0x140002cc7  xor     rcx, rsp; StackCookie
0x140002cca  call    __security_check_cookie
0x140002ccf  mov     rbx, [rsp+80h+arg_10]
0x140002cd7  add     rsp, 80h
0x140002cde  pop     r15
0x140002ce0  pop     r14
0x140002ce2  pop     r13
0x140002ce4  pop     r12
0x140002ce6  pop     rdi
0x140002ce7  pop     rsi
0x140002ce8  pop     rbp
0x140002ce9  retn
0x140002ceb  mov     rdi, r13
0x140002cee  sub     r9d, 22044Bh
0x140002cf5  jz      loc_140002C64
0x140002cfb  sub     r9d, 4
0x140002cff  jz      loc_140002C64
0x140002d05  sub     r9d, 3FB9h
0x140002d0c  jz      loc_140002F61
0x140002d12  sub     r9d, 0Ch
0x140002d16  jz      short loc_140002D29
0x140002d18  cmp     r9d, 4
0x140002d1c  jnz     loc_140002C64
0x140002d22  call    ?QueryDeviceText@CUsbBusFilter@@AEAAXPEAUWDFREQUEST__@@_K@Z; CUsbBusFilter::QueryDeviceText(WDFREQUEST__ *,unsigned __int64)
0x140002d27  jmp     short loc_140002CC3
0x140002d29  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002d30  lea     rcx, [rbp+var_50]
0x140002d34  mov     [rbp+psz], r13
0x140002d38  lea     r9, [rbp+psz]
0x140002d3c  mov     [rbp+var_50], r13
0x140002d40  mov     r8d, 2
0x140002d46  mov     [rbp+var_38], r13
0x140002d4a  mov     [rbp+var_30], r13
0x140002d4e  mov     rax, [rax+868h]
0x140002d55  mov     [rsp+80h+var_60], rcx
0x140002d5a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002d61  call    _guard_dispatch_icall
0x140002d66  mov     ebx, eax
0x140002d68  test    eax, eax
0x140002d6a  jns     short loc_140002DAA
0x140002d6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d73  lea     rax, WPP_GLOBAL_Control
0x140002d7a  cmp     rcx, rax
0x140002d7d  jz      loc_140002CA0
0x140002d83  cmp     byte ptr [rcx+29h], 2
0x140002d87  jb      loc_140002CA0
0x140002d8d  mov     edx, 1Fh
0x140002d92  mov     rcx, [rcx+18h]
0x140002d96  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140002d9d  mov     r9d, ebx
0x140002da0  call    WPP_SF_d
0x140002da5  jmp     loc_140002CA0
0x140002daa  mov     rcx, [rbp+psz]; psz
0x140002dae  mov     [rbp+pcchLength], r13
0x140002db2  test    rcx, rcx
0x140002db5  jz      loc_140002F2D
0x140002dbb  mov     rdx, [rbp+var_50]
0x140002dbf  shr     rdx, 1; cchMax
0x140002dc2  cmp     rdx, 7FFFFFFFh
0x140002dc9  ja      loc_140002F2D
0x140002dcf  lea     r8, [rbp+pcchLength]; pcchLength
0x140002dd3  call    RtlStringLengthWorkerW
0x140002dd8  mov     ebx, eax
0x140002dda  test    eax, eax
0x140002ddc  js      loc_140002F32
0x140002de2  mov     rax, [rbp+pcchLength]
0x140002de6  lea     rcx, [rbp+var_30]
0x140002dea  add     rax, rax
0x140002ded  mov     [rsp+80h+var_60], rcx
0x140002df2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002df9  lea     r9, [rbp+var_38]
0x140002dfd  mov     [rbp+var_50], rax
0x140002e01  mov     r8d, 4
0x140002e07  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002e0e  mov     rdx, r15
0x140002e11  mov     rax, [rax+870h]
0x140002e18  call    _guard_dispatch_icall
0x140002e1d  mov     ebx, eax
0x140002e1f  test    eax, eax
0x140002e21  jns     short loc_140002E4E
0x140002e23  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e2a  lea     rax, WPP_GLOBAL_Control
0x140002e31  cmp     rcx, rax
0x140002e34  jz      loc_140002CA0
0x140002e3a  cmp     byte ptr [rcx+29h], 2
0x140002e3e  jb      loc_140002CA0
0x140002e44  mov     edx, 21h ; '!'
0x140002e49  jmp     loc_140002D92
0x140002e4e  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002e55  mov     rdx, [rsi]
0x140002e58  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002e5f  mov     rax, [rax+9B0h]
0x140002e66  call    _guard_dispatch_icall
0x140002e6b  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002e72  mov     rdx, [rsi+18h]
0x140002e76  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002e7d  mov     rax, [rax+70h]
0x140002e81  call    _guard_dispatch_icall
0x140002e86  mov     r14d, eax
0x140002e89  mov     ebx, r13d
0x140002e8c  test    eax, eax
0x140002e8e  jz      short loc_140002F0B
0x140002e90  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140002e97  mov     r8d, ebx
0x140002e9a  mov     rdx, [rsi+18h]
0x140002e9e  mov     rax, [rcx+90h]
0x140002ea5  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002eac  call    _guard_dispatch_icall
0x140002eb1  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140002eb8  mov     r12, rax
0x140002ebb  mov     r8, cs:off_14000F150
0x140002ec2  mov     rdx, r12
0x140002ec5  mov     rax, [rcx+650h]
0x140002ecc  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002ed3  call    _guard_dispatch_icall
0x140002ed8  mov     rcx, [rbp+psz]
0x140002edc  mov     r9, [rax+60h]
0x140002ee0  add     r9, 68h ; 'h'
0x140002ee4  add     r9, rax
0x140002ee7  sub     r9, rcx
0x140002eea  movzx   edx, word ptr [rcx]
0x140002eed  movzx   r8d, word ptr [rcx+r9]
0x140002ef2  sub     edx, r8d
0x140002ef5  jnz     short loc_140002F00
0x140002ef7  add     rcx, 2
0x140002efb  test    r8d, r8d
0x140002efe  jnz     short loc_140002EEA
0x140002f00  test    edx, edx
0x140002f02  jz      short loc_140002F15
0x140002f04  inc     ebx
0x140002f06  cmp     ebx, r14d
0x140002f09  jb      short loc_140002E90
0x140002f0b  mov     ebx, 0C0000225h
0x140002f10  jmp     loc_140003156
0x140002f15  test    r12, r12
0x140002f18  jz      short loc_140002F0B
0x140002f1a  mov     ecx, [rax+18h]
0x140002f1d  mov     edi, 4
0x140002f22  mov     rax, [rbp+var_38]
0x140002f26  mov     [rax], ecx
0x140002f28  jmp     loc_140003153
0x140002f2d  mov     ebx, 0C000000Dh
0x140002f32  mov     [rbp+var_50], r13
0x140002f36  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f3d  lea     rax, WPP_GLOBAL_Control
0x140002f44  cmp     rcx, rax
0x140002f47  jz      loc_140002CA0
0x140002f4d  cmp     byte ptr [rcx+29h], 2
0x140002f51  jb      loc_140002CA0
0x140002f57  mov     edx, 20h ; ' '
0x140002f5c  jmp     loc_140002D92
0x140002f61  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002f68  lea     rcx, [rbp+pcchLength]
0x140002f6c  mov     [rbp+var_38], r13
0x140002f70  lea     r9, [rbp+var_38]
0x140002f74  mov     [rbp+pcchLength], r13
0x140002f78  mov     r8d, 8
0x140002f7e  mov     [rbp+var_50], r13
0x140002f82  mov     [rbp+psz], r13
0x140002f86  mov     rax, [rax+868h]
0x140002f8d  mov     [rsp+80h+var_60], rcx
0x140002f92  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002f99  mov     [rbp+var_30], r13
0x140002f9d  call    _guard_dispatch_icall
0x140002fa2  mov     ebx, eax
0x140002fa4  test    eax, eax
0x140002fa6  jns     short loc_140002FD3
0x140002fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x140002faf  lea     rax, WPP_GLOBAL_Control
0x140002fb6  cmp     rcx, rax
0x140002fb9  jz      loc_140002CA0
0x140002fbf  cmp     byte ptr [rcx+29h], 2
0x140002fc3  jb      loc_140002CA0
0x140002fc9  mov     edx, 1Ah
0x140002fce  jmp     loc_140002D92
0x140002fd3  test    r14, r14
0x140002fd6  jz      short loc_140003039
0x140002fd8  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002fdf  lea     rcx, [rbp+psz]
0x140002fe3  mov     [rsp+80h+var_60], rcx
0x140002fe8  lea     r9, [rbp+var_50]
0x140002fec  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002ff3  mov     r8d, 2
0x140002ff9  mov     rdx, r15
0x140002ffc  mov     rax, [rax+870h]
0x140003003  call    _guard_dispatch_icall
0x140003008  mov     ebx, eax
0x14000300a  test    eax, eax
0x14000300c  jns     short loc_140003041
0x14000300e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003015  lea     rax, WPP_GLOBAL_Control
0x14000301c  cmp     rcx, rax
0x14000301f  jz      loc_140002CA0
0x140003025  cmp     byte ptr [rcx+29h], 2
0x140003029  jb      loc_140002CA0
0x14000302f  mov     edx, 1Bh
0x140003034  jmp     loc_140002D92
0x140003039  mov     [rbp+var_50], r13
0x14000303d  mov     [rbp+psz], r13
0x140003041  mov     r8, [rbp+var_38]
0x140003045  mov     rdx, [rbp+pcchLength]
0x140003049  mov     r9d, [r8+4]
0x14000304d  lea     ecx, [r9+8]
0x140003051  cmp     rcx, rdx
0x140003054  jbe     short loc_140003086
0x140003056  mov     ebx, 0C000000Dh
0x14000305b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003062  lea     rax, WPP_GLOBAL_Control
0x140003069  cmp     rcx, rax
0x14000306c  jz      loc_140002CA0
0x140003072  cmp     byte ptr [rcx+29h], 2
0x140003076  jb      loc_140002CA0
0x14000307c  mov     edx, 1Ch
0x140003081  jmp     loc_140002D92
0x140003086  lea     r14, [r8+8]
0x14000308a  mov     rax, r9
0x14000308d  add     r14, r9
0x140003090  jz      loc_140003178
0x140003096  sub     rdx, rax
0x140003099  sub     rdx, 8
0x14000309d  shr     rdx, 1; cchMax
0x1400030a0  cmp     rdx, 7FFFFFFFh
0x1400030a7  ja      loc_140003178
0x1400030ad  lea     r8, [rbp+var_28]; pcchLength
0x1400030b1  mov     rcx, r14; psz
0x1400030b4  call    RtlStringLengthWorkerW
0x1400030b9  mov     ebx, eax
0x1400030bb  test    eax, eax
0x1400030bd  js      loc_14000317D
0x1400030c3  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400030ca  mov     rdx, [rsi]
0x1400030cd  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
  ... truncated ...
```
