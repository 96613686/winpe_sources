# CUsbBusFilter::QueryDeviceText(WDFREQUEST__ *,unsigned __int64)

- ea: `0x140004480`
- end: `0x14000471c`
- name: `?QueryDeviceText@CUsbBusFilter@@AEAAXPEAUWDFREQUEST__@@_K@Z`
- size: `668`
- prototype: `void __fastcall(CUsbBusFilter *__hidden this, struct WDFREQUEST__ *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140002bc4`

## callees

- `0x140003f90`
- `0x140004480`
- `0x140005084`
- `0x14000a2e8`
- `0x14000aa30`
- `0x14000b140`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400046f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400046f7`

## pseudocode

```c
void __fastcall CUsbBusFilter::QueryDeviceText(CUsbBusFilter *this, struct WDFREQUEST__ *a2, __int64 a3)
{
  unsigned __int64 v5; // rdi
  struct _LIST_ENTRY *Blink; // rax
  int v8; // eax
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // r8
  const wchar_t *v12; // rbx
  size_t v13; // rdx
  NTSTATUS v14; // eax
  __int64 v15; // r11
  int v16; // eax
  size_t v17; // rbx
  void *v18; // rdx
  void *Src; // [rsp+40h] [rbp-40h] BYREF
  __int64 v20; // [rsp+48h] [rbp-38h] BYREF
  __int64 v21; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v22; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v23; // [rsp+60h] [rbp-20h] BYREF
  __int64 v24; // [rsp+68h] [rbp-18h] BYREF
  size_t pcchLength[2]; // [rsp+70h] [rbp-10h] BYREF
  _WORD *v26; // [rsp+B8h] [rbp+38h] BYREF

  v21 = 0;
  v22 = 0;
  v26 = 0;
  v20 = 0;
  v5 = 0;
  v24 = 0;
  Blink = WPP_MAIN_CB.Queue.ListEntry.Flink[134].Blink;
  v23 = 0;
  Src = 0;
  v8 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, __int64 *, unsigned __int64 *))Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2,
         12,
         &v21,
         &v22);
  v9 = (unsigned int)v8;
  if ( v8 < 0 )
    goto LABEL_23;
  if ( a3 )
  {
    v10 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, _WORD **, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[135].Flink)(
            WPP_MAIN_CB.Queue.ListEntry.Blink,
            a2,
            2,
            &v26,
            &v20);
    v9 = (unsigned int)v10;
    if ( v10 < 0 )
      goto LABEL_23;
  }
  else
  {
    v26 = 0;
    v20 = 0;
  }
  v11 = *(unsigned int *)(v21 + 4);
  if ( (unsigned int)(v11 + 12) <= v22
    && (v12 = (const wchar_t *)(v11 + v21 + 12)) != 0
    && (v13 = (v22 - (unsigned int)v11 - 12) >> 1, v13 <= 0x7FFFFFFF) )
  {
    v14 = RtlStringLengthWorkerW(v12, v13, pcchLength);
    v9 = (unsigned int)v14;
    if ( v14 >= 0 )
    {
      v16 = CUsbBusFilter::QueryChildDeviceText(
              this,
              0,
              v12,
              DeviceTextDescription,
              *(_DWORD *)(v15 + 8),
              (unsigned __int16 **)&Src,
              &v23);
      v9 = (unsigned int)v16;
      if ( v16 >= 0 )
      {
        v17 = v23 + 2;
        v5 = v23 + 4;
        if ( ((int (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, unsigned __int64, _WORD **, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[135].Flink)(
               WPP_MAIN_CB.Queue.ListEntry.Blink,
               a2,
               v23 + 4,
               &v26,
               &v24) >= 0 )
        {
          if ( v17 <= 0xFFFF )
          {
            v18 = Src;
            *v26 = v17 >> 1;
            memmove(v26 + 1, v18, v17);
            v9 = 0;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids);
            v5 = 0;
            v9 = 3221225701LL;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids);
          v9 = 2147483653LL;
        }
      }
    }
  }
  else
  {
    v9 = 3221225485LL;
  }
LABEL_23:
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, unsigned __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[132].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    v9,
    v5);
  if ( Src )
    ExFreePoolWithTag(Src, 0);
}

```

## disassembly

```asm
0x140004480  mov     [rsp-18h+arg_0], rbx
0x140004485  mov     [rsp-18h+arg_8], rsi
0x14000448a  push    rbp
0x14000448b  push    rdi
0x14000448c  push    r14
0x14000448e  mov     rbp, rsp
0x140004491  sub     rsp, 80h
0x140004498  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000449f  lea     r9, [rbp+var_30]
0x1400044a3  mov     r14, rcx
0x1400044a6  mov     [rbp+var_30], 0
0x1400044ae  lea     rcx, [rbp+var_28]
0x1400044b2  mov     [rbp+var_28], 0
0x1400044ba  mov     rbx, r8
0x1400044bd  mov     [rbp+arg_18], 0
0x1400044c5  mov     [rbp+var_38], 0
0x1400044cd  xor     edi, edi
0x1400044cf  mov     [rbp+var_18], 0
0x1400044d7  mov     rsi, rdx
0x1400044da  mov     rax, [rax+868h]
0x1400044e1  mov     qword ptr [rsp+80h+var_60], rcx
0x1400044e6  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400044ed  lea     r8d, [rdi+0Ch]
0x1400044f1  mov     [rbp+var_20], 0
0x1400044f9  mov     [rbp+Src], 0
0x140004501  call    _guard_dispatch_icall
0x140004506  mov     r8d, eax
0x140004509  test    eax, eax
0x14000450b  js      loc_1400046CC
0x140004511  test    rbx, rbx
0x140004514  jz      short loc_140004551
0x140004516  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000451d  lea     rcx, [rbp+var_38]
0x140004521  mov     qword ptr [rsp+80h+var_60], rcx
0x140004526  lea     r9, [rbp+arg_18]
0x14000452a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140004531  lea     r8d, [rdi+2]
0x140004535  mov     rdx, rsi
0x140004538  mov     rax, [rax+870h]
0x14000453f  call    _guard_dispatch_icall
0x140004544  mov     r8d, eax
0x140004547  test    eax, eax
0x140004549  js      loc_1400046CC
0x14000454f  jmp     short loc_140004559
0x140004551  mov     [rbp+arg_18], rdi
0x140004555  mov     [rbp+var_38], rdi
0x140004559  mov     r11, [rbp+var_30]
0x14000455d  mov     rdx, [rbp+var_28]
0x140004561  mov     r8d, [r11+4]
0x140004565  lea     ecx, [r8+0Ch]
0x140004569  cmp     rcx, rdx
0x14000456c  ja      loc_1400046C6
0x140004572  lea     rbx, [r11+0Ch]
0x140004576  mov     eax, r8d
0x140004579  add     rbx, r8
0x14000457c  jz      loc_1400046C6
0x140004582  sub     rdx, rax
0x140004585  sub     rdx, 0Ch
0x140004589  shr     rdx, 1; cchMax
0x14000458c  cmp     rdx, 7FFFFFFFh
0x140004593  ja      loc_1400046C6
0x140004599  lea     r8, [rbp+pcchLength]; pcchLength
0x14000459d  mov     rcx, rbx; psz
0x1400045a0  call    RtlStringLengthWorkerW
0x1400045a5  mov     r8d, eax
0x1400045a8  test    eax, eax
0x1400045aa  js      loc_1400046CC
0x1400045b0  lea     rax, [rbp+var_20]
0x1400045b4  xor     r9d, r9d; enum DEVICE_TEXT_TYPE
0x1400045b7  mov     [rsp+80h+var_50], rax; unsigned __int64 *
0x1400045bc  mov     r8, rbx; unsigned __int16 *
0x1400045bf  lea     rax, [rbp+Src]
0x1400045c3  xor     edx, edx; struct _DEVICE_OBJECT *
0x1400045c5  mov     [rsp+80h+var_58], rax; unsigned __int16 **
0x1400045ca  mov     rcx, r14; this
0x1400045cd  mov     eax, [r11+8]
0x1400045d1  mov     [rsp+80h+var_60], eax; unsigned int
0x1400045d5  call    ?QueryChildDeviceText@CUsbBusFilter@@AEAAJPEAU_DEVICE_OBJECT@@PEBGW4DEVICE_TEXT_TYPE@@KPEAPEBGPEA_K@Z; CUsbBusFilter::QueryChildDeviceText(_DEVICE_OBJECT *,ushort const *,DEVICE_TEXT_TYPE,ulong,ushort const * *,unsigned __int64 *)
0x1400045da  mov     r8d, eax
0x1400045dd  test    eax, eax
0x1400045df  js      loc_1400046CC
0x1400045e5  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400045ec  lea     rcx, [rbp+var_18]
0x1400045f0  mov     rbx, [rbp+var_20]
0x1400045f4  lea     r9, [rbp+arg_18]
0x1400045f8  mov     qword ptr [rsp+80h+var_60], rcx
0x1400045fd  add     rbx, 2
0x140004601  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140004608  mov     rdx, rsi
0x14000460b  mov     rax, [rax+870h]
0x140004612  lea     rdi, [rbx+2]
0x140004616  mov     r8, rdi
0x140004619  call    _guard_dispatch_icall
0x14000461e  test    eax, eax
0x140004620  jns     short loc_14000465C
0x140004622  mov     rcx, cs:WPP_GLOBAL_Control
0x140004629  lea     rax, WPP_GLOBAL_Control
0x140004630  cmp     rcx, rax
0x140004633  jz      short loc_140004654
0x140004635  cmp     byte ptr [rcx+29h], 2
0x140004639  jb      short loc_140004654
0x14000463b  mov     r9, [rbp+var_18]
0x14000463f  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140004646  mov     rcx, [rcx+18h]
0x14000464a  mov     edx, 18h
0x14000464f  call    WPP_SF_i
0x140004654  mov     r8d, 80000005h
0x14000465a  jmp     short loc_1400046CC
0x14000465c  cmp     rbx, 0FFFFh
0x140004663  jbe     short loc_1400046A0
0x140004665  mov     rcx, cs:WPP_GLOBAL_Control
0x14000466c  lea     rax, WPP_GLOBAL_Control
0x140004673  cmp     rcx, rax
0x140004676  jz      short loc_140004696
0x140004678  cmp     byte ptr [rcx+29h], 2
0x14000467c  jb      short loc_140004696
0x14000467e  mov     rcx, [rcx+18h]
0x140004682  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140004689  mov     edx, 19h
0x14000468e  mov     r9, rbx
0x140004691  call    WPP_SF_i
0x140004696  xor     edi, edi
0x140004698  mov     r8d, 0C00000E5h
0x14000469e  jmp     short loc_1400046CC
0x1400046a0  mov     rax, [rbp+arg_18]
0x1400046a4  mov     rcx, rbx
0x1400046a7  mov     rdx, [rbp+Src]; Src
0x1400046ab  mov     r8, rbx; Size
0x1400046ae  shr     rcx, 1
0x1400046b1  mov     [rax], cx
0x1400046b4  mov     rcx, [rbp+arg_18]
0x1400046b8  add     rcx, 2; void *
0x1400046bc  call    memmove
0x1400046c1  xor     r8d, r8d
0x1400046c4  jmp     short loc_1400046CC
0x1400046c6  mov     r8d, 0C000000Dh
0x1400046cc  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400046d3  mov     r9, rdi
0x1400046d6  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400046dd  mov     rdx, rsi
0x1400046e0  mov     rax, [rax+848h]
0x1400046e7  call    _guard_dispatch_icall
0x1400046ec  mov     rcx, [rbp+Src]; P
0x1400046f0  test    rcx, rcx
0x1400046f3  jz      short loc_140004703
0x1400046f5  xor     edx, edx; Tag
0x1400046f7  call    cs:__imp_ExFreePoolWithTag
0x1400046fe  nop     dword ptr [rax+rax+00h]
0x140004703  lea     r11, [rsp+80h+var_s0]
0x14000470b  mov     rbx, [r11+20h]
0x14000470f  mov     rsi, [r11+28h]
0x140004713  mov     rsp, r11
0x140004716  pop     r14
0x140004718  pop     rdi
0x140004719  pop     rbp
0x14000471a  retn
```
