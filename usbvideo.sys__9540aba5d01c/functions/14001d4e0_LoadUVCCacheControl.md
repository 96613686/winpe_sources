# LoadUVCCacheControl

- ea: `0x14001d4e0`
- end: `0x14001d7b4`
- name: `LoadUVCCacheControl`
- size: `724`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001fcb0`

## callees

- `0x140008640`
- `0x14000e964`
- `0x14001ab4c`
- `0x14001d4e0`
- `0x14001e1e4`
- `0x14001e28c`

## import_xrefs

- `ks!KsReleaseDevice` at `0x14001d758`
- `ks!KsReleaseDevice` at `0x14001d758`
- `ks!KsAcquireDevice` at `0x14001d63e`
- `ks!KsAcquireDevice` at `0x14001d63e`

## pseudocode

```c
__int64 __fastcall LoadUVCCacheControl(__int64 a1, signed int a2, int a3)
{
  unsigned int DeviceRegValueDword; // edi
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // r14
  __int64 v9; // rbp
  unsigned int v10; // eax
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  int v14; // eax
  int v16; // [rsp+20h] [rbp-68h]
  size_t Size; // [rsp+30h] [rbp-58h]
  int v18; // [rsp+90h] [rbp+8h] BYREF

  v18 = 0;
  if ( a1 )
  {
    if ( *(_QWORD *)(a1 + 24) )
    {
      if ( (unsigned int)a2 <= 9 )
      {
        v8 = a2;
        v9 = 3LL * a2;
        if ( LODWORD(qword_140045500[3 * a2 + 2]) <= 4 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_qS(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, qword_140045500[3 * a2 + 1]);
          *(_DWORD *)(a1 + 8 * v8 + 1432) = -1;
          *(_DWORD *)(a1 + 8 * v8 + 1428) = 0;
          DeviceRegValueDword = GetDeviceRegValueDword(
                                  *(struct _DEVICE_OBJECT **)(*(_QWORD *)(a1 + 24) + 32LL),
                                  1u,
                                  (const WCHAR *)qword_140045500[v9 + 1],
                                  &v18);
          if ( (DeviceRegValueDword & 0x80000000) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_qDS(
                WPP_GLOBAL_Control->AttachedDevice,
                75,
                (unsigned int)WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids,
                a1,
                DeviceRegValueDword,
                qword_140045500[v9 + 1]);
            return DeviceRegValueDword;
          }
          KsAcquireDevice(*(PKSDEVICE *)(a1 + 24));
          v10 = *(_DWORD *)(a1 + 176);
          if ( v10 < *(_DWORD *)(a1 + 112) )
          {
            v13 = *(_QWORD *)(a1 + 120) + *(_DWORD *)(a1 + 116) * v10;
            v10 = *(_DWORD *)(v13 + 44);
            if ( v10 == 5 )
            {
              LODWORD(Size) = qword_140045500[v9 + 2];
              LOBYTE(v16) = *(_BYTE *)(v13 + 40);
              v14 = SubmitControlRequest(
                      0x21u,
                      1u,
                      LOWORD(qword_140045500[v9]) << 8,
                      *(_BYTE *)(*(_QWORD *)(v13 + 32) + 3LL),
                      v16,
                      (unsigned __int8 *)&v18,
                      Size,
                      v13,
                      a1);
              DeviceRegValueDword = v14;
              if ( v14 < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  WPP_SF_qD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    78,
                    WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids,
                    a1,
                    v14);
              }
              else
              {
                *(_DWORD *)(a1 + 8 * v8 + 1432) = v18;
              }
              KsReleaseDevice(*(PKSDEVICE *)(a1 + 24));
              return DeviceRegValueDword;
            }
            DeviceRegValueDword = -1073741823;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
              return DeviceRegValueDword;
            v12 = 77;
          }
          else
          {
            DeviceRegValueDword = -1073741823;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
              return DeviceRegValueDword;
            v12 = 76;
          }
          WPP_SF_qD(v11->AttachedDevice, v12, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, a1, v10);
          return DeviceRegValueDword;
        }
      }
      DeviceRegValueDword = -1073741811;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return DeviceRegValueDword;
      v6 = 73;
    }
    else
    {
      DeviceRegValueDword = -1073741811;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return DeviceRegValueDword;
      v6 = 72;
    }
    v7 = a1;
    goto LABEL_37;
  }
  DeviceRegValueDword = -1073741811;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v6 = 71;
    v7 = 0;
LABEL_37:
    WPP_SF_qD(v5->AttachedDevice, v6, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids, v7, -1073741811);
  }
  return DeviceRegValueDword;
}

```

## disassembly

```asm
0x14001d4e0  mov     rax, rsp
0x14001d4e3  push    rbx
0x14001d4e4  push    rbp
0x14001d4e5  push    rsi
0x14001d4e6  push    rdi
0x14001d4e7  push    r12
0x14001d4e9  push    r14
0x14001d4eb  sub     rsp, 58h
0x14001d4ef  mov     dword ptr [rax+8], 0
0x14001d4f6  mov     rbx, rcx
0x14001d4f9  test    rcx, rcx
0x14001d4fc  jnz     short loc_14001D52F
0x14001d4fe  mov     edi, 0C000000Dh
0x14001d503  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d50a  lea     rsi, WPP_GLOBAL_Control
0x14001d511  cmp     rcx, rsi
0x14001d514  jz      loc_14001D7A4
0x14001d51a  cmp     byte ptr [rcx+29h], 2
0x14001d51e  jb      loc_14001D7A4
0x14001d524  lea     edx, [rbx+47h]
0x14001d527  xor     r9d, r9d
0x14001d52a  jmp     loc_14001D78C
0x14001d52f  cmp     qword ptr [rcx+18h], 0
0x14001d534  jnz     short loc_14001D566
0x14001d536  mov     edi, 0C000000Dh
0x14001d53b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d542  lea     rsi, WPP_GLOBAL_Control
0x14001d549  cmp     rcx, rsi
0x14001d54c  jz      loc_14001D7A4
0x14001d552  cmp     byte ptr [rcx+29h], 2
0x14001d556  jb      loc_14001D7A4
0x14001d55c  mov     edx, 48h ; 'H'
0x14001d561  jmp     loc_14001D789
0x14001d566  cmp     edx, 9
0x14001d569  ja      loc_14001D766
0x14001d56f  movsxd  r14, edx
0x14001d572  lea     r12, qword_140045500
0x14001d579  lea     rbp, [r14+r14*2]
0x14001d57d  cmp     dword ptr [r12+rbp*8+10h], 4
0x14001d583  ja      loc_14001D766
0x14001d589  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d590  lea     rsi, WPP_GLOBAL_Control
0x14001d597  cmp     rcx, rsi
0x14001d59a  jz      short loc_14001D5B8
0x14001d59c  cmp     byte ptr [rcx+29h], 4
0x14001d5a0  jb      short loc_14001D5B8
0x14001d5a2  mov     rax, [r12+rbp*8+8]
0x14001d5a7  mov     r9, rbx
0x14001d5aa  mov     rcx, [rcx+18h]
0x14001d5ae  mov     qword ptr [rsp+88h+var_68], rax
0x14001d5b3  call    WPP_SF_qS
0x14001d5b8  mov     dword ptr [rbx+r14*8+598h], 0FFFFFFFFh
0x14001d5c4  lea     r9, [rsp+88h+arg_0]
0x14001d5cc  mov     dword ptr [rbx+r14*8+594h], 0
0x14001d5d8  mov     edx, 1
0x14001d5dd  mov     rcx, [rbx+18h]
0x14001d5e1  mov     r8, [r12+rbp*8+8]
0x14001d5e6  mov     rcx, [rcx+20h]
0x14001d5ea  call    GetDeviceRegValueDword
0x14001d5ef  mov     edi, eax
0x14001d5f1  test    eax, eax
0x14001d5f3  jns     short loc_14001D63A
0x14001d5f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d5fc  cmp     rcx, rsi
0x14001d5ff  jz      loc_14001D7A4
0x14001d605  cmp     byte ptr [rcx+29h], 2
0x14001d609  jb      loc_14001D7A4
0x14001d60f  mov     rax, [r12+rbp*8+8]
0x14001d614  lea     r8, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x14001d61b  mov     rcx, [rcx+18h]
0x14001d61f  mov     edx, 4Bh ; 'K'
0x14001d624  mov     [rsp+88h+var_60], rax
0x14001d629  mov     r9, rbx
0x14001d62c  mov     [rsp+88h+var_68], edi
0x14001d630  call    WPP_SF_qDS
0x14001d635  jmp     loc_14001D7A4
0x14001d63a  mov     rcx, [rbx+18h]; Device
0x14001d63e  call    cs:__imp_KsAcquireDevice
0x14001d645  nop     dword ptr [rax+rax+00h]
0x14001d64a  mov     eax, [rbx+0B0h]
0x14001d650  cmp     eax, [rbx+70h]
0x14001d653  jb      short loc_14001D695
0x14001d655  mov     edi, 0C0000001h
0x14001d65a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d661  cmp     rcx, rsi
0x14001d664  jz      loc_14001D7A4
0x14001d66a  cmp     byte ptr [rcx+29h], 5
0x14001d66e  jb      loc_14001D7A4
0x14001d674  mov     edx, 4Ch ; 'L'
0x14001d679  mov     rcx, [rcx+18h]
0x14001d67d  lea     r8, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x14001d684  mov     r9, rbx
0x14001d687  mov     [rsp+88h+var_68], eax
0x14001d68b  call    WPP_SF_qD
0x14001d690  jmp     loc_14001D7A4
0x14001d695  imul    eax, [rbx+74h]
0x14001d699  mov     edx, eax
0x14001d69b  add     rdx, [rbx+78h]
0x14001d69f  mov     eax, [rdx+2Ch]
0x14001d6a2  cmp     eax, 5
0x14001d6a5  jz      short loc_14001D6CD
0x14001d6a7  mov     edi, 0C0000001h
0x14001d6ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d6b3  cmp     rcx, rsi
0x14001d6b6  jz      loc_14001D7A4
0x14001d6bc  cmp     byte ptr [rcx+29h], 5
0x14001d6c0  jb      loc_14001D7A4
0x14001d6c6  mov     edx, 4Dh ; 'M'
0x14001d6cb  jmp     short loc_14001D679
0x14001d6cd  mov     eax, [r12+rbp*8+10h]
0x14001d6d2  mov     cl, 21h ; '!'; int
0x14001d6d4  mov     r9, [rdx+20h]
0x14001d6d8  movzx   r8d, word ptr [r12+rbp*8]
0x14001d6dd  mov     [rsp+88h+var_48], rbx; __int64
0x14001d6e2  mov     [rsp+88h+var_50], rdx; __int64
0x14001d6e7  mov     r9b, [r9+3]; int
0x14001d6eb  mov     dword ptr [rsp+88h+Size], eax; Size
0x14001d6ef  lea     rax, [rsp+88h+arg_0]
0x14001d6f7  mov     [rsp+88h+var_60], rax; void *
0x14001d6fc  mov     al, [rdx+28h]
0x14001d6ff  mov     dl, 1; int
0x14001d701  shl     r8w, 8; int
0x14001d706  mov     byte ptr [rsp+88h+var_68], al; int
0x14001d70a  call    SubmitControlRequest
0x14001d70f  mov     edi, eax
0x14001d711  test    eax, eax
0x14001d713  js      short loc_14001D726
0x14001d715  mov     eax, [rsp+88h+arg_0]
0x14001d71c  mov     [rbx+r14*8+598h], eax
0x14001d724  jmp     short loc_14001D754
0x14001d726  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d72d  cmp     rcx, rsi
0x14001d730  jz      short loc_14001D754
0x14001d732  cmp     byte ptr [rcx+29h], 2
0x14001d736  jb      short loc_14001D754
0x14001d738  mov     rcx, [rcx+18h]
0x14001d73c  lea     r8, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x14001d743  mov     edx, 4Eh ; 'N'
0x14001d748  mov     [rsp+88h+var_68], eax
0x14001d74c  mov     r9, rbx
0x14001d74f  call    WPP_SF_qD
0x14001d754  mov     rcx, [rbx+18h]; Device
0x14001d758  call    cs:__imp_KsReleaseDevice
0x14001d75f  nop     dword ptr [rax+rax+00h]
0x14001d764  jmp     short loc_14001D7A4
0x14001d766  mov     edi, 0C000000Dh
0x14001d76b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d772  lea     rsi, WPP_GLOBAL_Control
0x14001d779  cmp     rcx, rsi
0x14001d77c  jz      short loc_14001D7A4
0x14001d77e  cmp     byte ptr [rcx+29h], 2
0x14001d782  jb      short loc_14001D7A4
0x14001d784  mov     edx, 49h ; 'I'
0x14001d789  mov     r9, rbx
0x14001d78c  mov     rcx, [rcx+18h]
0x14001d790  lea     r8, WPP_5eeb60afc7363d0bc6b5cd37ec4f326c_Traceguids
0x14001d797  mov     [rsp+88h+var_68], 0C000000Dh
0x14001d79f  call    WPP_SF_qD
0x14001d7a4  mov     eax, edi
0x14001d7a6  add     rsp, 58h
0x14001d7aa  pop     r14
0x14001d7ac  pop     r12
0x14001d7ae  pop     rdi
0x14001d7af  pop     rsi
0x14001d7b0  pop     rbp
0x14001d7b1  pop     rbx
0x14001d7b2  retn
```
