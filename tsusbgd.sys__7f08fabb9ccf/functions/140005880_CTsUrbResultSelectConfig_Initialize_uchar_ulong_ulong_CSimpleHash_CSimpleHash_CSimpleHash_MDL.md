# CTsUrbResultSelectConfig::Initialize(uchar *,ulong,ulong,CSimpleHash *,CSimpleHash *,CSimpleHash *,_MDL *)

- ea: `0x140005880`
- end: `0x140005b82`
- name: `?Initialize@CTsUrbResultSelectConfig@@EEAAJPEAEKKPEAVCSimpleHash@@11PEAU_MDL@@@Z`
- size: `770`
- prototype: `__int64 __fastcall(CTsUrbResultSelectConfig *__hidden this, unsigned __int8 *, unsigned int, unsigned int, struct CSimpleHash *, struct CSimpleHash *, struct CSimpleHash *, struct _MDL *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x140003964`
- `0x14000491c`
- `0x140005880`
- `0x140006440`
- `0x140006a80`

## pseudocode

```c
__int64 __fastcall CTsUrbResultSelectConfig::Initialize(
        CTsUrbResultSelectConfig *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int a4,
        struct CSimpleHash *a5,
        struct CSimpleHash *a6,
        struct CSimpleHash *a7,
        struct _MDL *a8)
{
  unsigned int v10; // r9d
  unsigned int v11; // ebx
  unsigned __int8 *v12; // r15
  unsigned int v13; // r14d
  unsigned int v14; // edx
  unsigned __int8 *v15; // rsi
  unsigned int v16; // r12d
  __int64 v17; // rax
  unsigned int v18; // r10d
  unsigned int v19; // ecx
  unsigned int v20; // r8d
  __int64 v21; // rdi
  unsigned int v22; // ecx
  unsigned int v23; // r11d
  unsigned int v24; // r13d
  unsigned int v25; // eax
  struct _URB *Urb; // rax
  struct _URB *v27; // rdi
  USBD_INTERFACE_INFORMATION *p_Interface; // r14
  unsigned int v29; // edi
  USHORT v30; // bx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rcx
  char *v34; // rcx
  struct _URB *v35; // [rsp+30h] [rbp-48h]

  if ( !a8 && a3 >= 0x10 && *(unsigned __int16 *)a2 == a3 )
  {
    v10 = *((_DWORD *)a2 + 3);
    if ( v10 )
    {
      v11 = 40;
      v12 = a2 + 16;
      v13 = 0;
      v14 = a3 - 16;
      v15 = a2 + 16;
      v16 = 16;
      while ( v14 >= 0xC )
      {
        v17 = *((unsigned int *)v15 + 2);
        v18 = *((unsigned __int16 *)v15 + 1);
        if ( v18 < (unsigned int)v17 )
          break;
        v19 = 12 * v17;
        if ( (unsigned __int64)(12 * v17) > 0xFFFFFFFF )
          return 3221225621LL;
        v20 = v19 + 12;
        if ( v19 >= 0xFFFFFFF4 )
          return 3221225621LL;
        v21 = *(unsigned __int16 *)v15;
        if ( (_DWORD)v21 != v20 || v20 > v14 )
          return 3221225485LL;
        v22 = 24 * (v18 + 1);
        if ( v22 < 0x18 )
          return 3221225621LL;
        v23 = v22 + v11;
        if ( v22 + v11 < v11 || 20 * v18 >= 0xFFFFFFF0 || v16 + 20 * v18 + 16 < v16 )
          return 3221225621LL;
        v14 -= v20;
        v15 += v21;
        ++v13;
        v11 += v22;
        v16 += 20 * v18 + 16;
        if ( v13 >= v10 )
        {
          if ( a2[8] )
          {
            if ( v14 < 9 )
              return 3221225485LL;
            if ( *v15 != 9 )
              return 3221225485LL;
            if ( v15[4] != v10 )
              return 3221225485LL;
            v24 = *((unsigned __int16 *)v15 + 1);
            if ( v24 != v14 )
              return 3221225485LL;
            v25 = v23 + v24;
            if ( v23 + v24 < v23 )
              return 3221225621LL;
            v14 = 0;
          }
          else
          {
            v15 = 0;
            v25 = v23;
            v24 = 0;
          }
          if ( v25 > 0xFFFF || v14 || v16 > 0xFFFF )
            return 3221225485LL;
          if ( v16 > a4 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_DD(
                WPP_GLOBAL_Control->AttachedDevice,
                11,
                WPP_33b5c1abd2bc3b5ab5f1e33a32ecfbc2_Traceguids,
                a4,
                v16);
            return 3221225485LL;
          }
          Urb = CTsUrbResult::AllocateUrb(this, v25);
          v35 = Urb;
          v27 = Urb;
          if ( !Urb )
            return 3221225495LL;
          p_Interface = &Urb->UrbSelectConfiguration.Interface;
          *(_OWORD *)&Urb->UrbHeader.Length = 0;
          *(_OWORD *)&Urb->UrbControlVendorClassRequest.Hdr.UsbdFlags = 0;
          Urb->UrbSelectConfiguration.ConfigurationHandle = 0;
          Urb->UrbHeader.Length = v11;
          Urb->UrbHeader.Function = *((_WORD *)a2 + 1);
          if ( *((_DWORD *)a2 + 3) )
          {
            v29 = 0;
            do
            {
              v30 = 24 * (*((_WORD *)v12 + 1) + 1);
              memset(p_Interface, 0, 24 * ((unsigned int)*((unsigned __int16 *)v12 + 1) + 1));
              p_Interface->Length = v30;
              v31 = 0;
              p_Interface->InterfaceNumber = v12[4];
              p_Interface->AlternateSetting = v12[5];
              for ( p_Interface->NumberOfPipes = *((_DWORD *)v12 + 2);
                    (unsigned int)v31 < *((_DWORD *)v12 + 2);
                    p_Interface->Pipes[v33].PipeFlags = *(_DWORD *)&v12[4 * v32 + 20] )
              {
                v32 = 3 * v31;
                v33 = v31;
                p_Interface->Pipes[v33].MaximumPacketSize = *(_WORD *)&v12[12 * v31 + 12];
                v31 = (unsigned int)(v31 + 1);
                p_Interface->Pipes[v33].MaximumTransferSize = *(_DWORD *)&v12[4 * v32 + 16];
              }
              ++v29;
              p_Interface = (USBD_INTERFACE_INFORMATION *)((char *)p_Interface + p_Interface->Length);
              v12 += *(unsigned __int16 *)v12;
            }
            while ( v29 < *((_DWORD *)a2 + 3) );
            v27 = v35;
          }
          if ( v15 )
          {
            v34 = (char *)v27 + v27->UrbHeader.Length;
            v27->UrbSelectInterface.ConfigurationHandle = v34;
            memmove(v34, v15, v24);
          }
          *((_WORD *)this + 853) = v16;
          *((_BYTE *)this + 1720) = a2[12];
          return 0;
        }
      }
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140005880  mov     [rsp+arg_8], rbx
0x140005885  mov     [rsp+arg_18], r9d
0x14000588a  mov     [rsp+arg_0], rcx
0x14000588f  push    rbp
0x140005890  push    rsi
0x140005891  push    rdi
0x140005892  push    r12
0x140005894  push    r13
0x140005896  push    r14
0x140005898  push    r15
0x14000589a  sub     rsp, 40h
0x14000589e  cmp     [rsp+78h+arg_38], 0
0x1400058a7  mov     r10d, r9d
0x1400058aa  mov     rbp, rdx
0x1400058ad  jz      short loc_1400058B9
0x1400058af  mov     eax, 0C000000Dh
0x1400058b4  jmp     loc_140005B69
0x1400058b9  cmp     r8d, 10h
0x1400058bd  jb      short loc_1400058AF
0x1400058bf  movzx   eax, word ptr [rdx]
0x1400058c2  cmp     eax, r8d
0x1400058c5  jnz     short loc_1400058AF
0x1400058c7  mov     r9d, [rdx+0Ch]
0x1400058cb  test    r9d, r9d
0x1400058ce  jz      short loc_1400058AF
0x1400058d0  mov     ebx, 28h ; '('
0x1400058d5  lea     r15, [rbp+10h]
0x1400058d9  xor     r14d, r14d
0x1400058dc  lea     edx, [r8-10h]
0x1400058e0  mov     rsi, r15
0x1400058e3  lea     r12d, [rbx-18h]
0x1400058e7  test    r9d, r9d
0x1400058ea  jz      loc_140005993
0x1400058f0  cmp     edx, 0Ch
0x1400058f3  jb      short loc_1400058AF
0x1400058f5  mov     eax, [rsi+8]
0x1400058f8  movzx   r10d, word ptr [rsi+2]
0x1400058fd  cmp     r10d, eax
0x140005900  jb      short loc_1400058AF
0x140005902  lea     rcx, [rax+rax*2]
0x140005906  mov     eax, 0FFFFFFFFh
0x14000590b  shl     rcx, 2
0x14000590f  cmp     rcx, rax
0x140005912  ja      loc_1400059D2
0x140005918  lea     r8d, [rcx+0Ch]
0x14000591c  cmp     r8d, 0Ch
0x140005920  jb      loc_1400059D2
0x140005926  movzx   edi, word ptr [rsi]
0x140005929  cmp     edi, r8d
0x14000592c  jnz     short loc_1400058AF
0x14000592e  cmp     r8d, edx
0x140005931  ja      loc_1400058AF
0x140005937  lea     eax, [r10+1]
0x14000593b  lea     ecx, [rax+rax*2]
0x14000593e  shl     ecx, 3
0x140005941  cmp     ecx, 18h
0x140005944  jb      loc_1400059D2
0x14000594a  lea     r11d, [rcx+rbx]
0x14000594e  cmp     r11d, ebx
0x140005951  jb      short loc_1400059D2
0x140005953  lea     eax, [r10+r10*4]
0x140005957  lea     eax, ds:10h[rax*4]
0x14000595e  cmp     eax, 10h
0x140005961  jb      short loc_1400059D2
0x140005963  add     eax, r12d
0x140005966  cmp     eax, r12d
0x140005969  jb      short loc_1400059D2
0x14000596b  sub     edx, r8d
0x14000596e  add     rsi, rdi
0x140005971  inc     r14d
0x140005974  mov     ebx, r11d
0x140005977  mov     r12d, eax
0x14000597a  cmp     r14d, r9d
0x14000597d  jb      loc_1400058F0
0x140005983  mov     r10d, [rsp+78h+arg_18]
0x14000598b  mov     rcx, [rsp+78h+arg_0]; this
0x140005993  cmp     byte ptr [rbp+8], 0
0x140005997  jz      short loc_1400059DC
0x140005999  cmp     edx, 9
0x14000599c  jb      loc_1400058AF
0x1400059a2  cmp     byte ptr [rsi], 9
0x1400059a5  jnz     loc_1400058AF
0x1400059ab  movzx   eax, byte ptr [rsi+4]
0x1400059af  cmp     eax, r9d
0x1400059b2  jnz     loc_1400058AF
0x1400059b8  movzx   r13d, word ptr [rsi+2]
0x1400059bd  cmp     r13d, edx
0x1400059c0  jnz     loc_1400058AF
0x1400059c6  lea     eax, [rbx+r13]
0x1400059ca  cmp     eax, ebx
0x1400059cc  jb      short loc_1400059D2
0x1400059ce  xor     edx, edx
0x1400059d0  jmp     short loc_1400059E3
0x1400059d2  mov     eax, 0C0000095h
0x1400059d7  jmp     loc_140005B69
0x1400059dc  xor     esi, esi
0x1400059de  mov     eax, ebx
0x1400059e0  xor     r13d, r13d
0x1400059e3  mov     r8d, 0FFFFh
0x1400059e9  cmp     eax, r8d
0x1400059ec  ja      loc_1400058AF
0x1400059f2  test    edx, edx
0x1400059f4  jnz     loc_1400058AF
0x1400059fa  cmp     r12d, r8d
0x1400059fd  ja      loc_1400058AF
0x140005a03  cmp     r12d, r10d
0x140005a06  jbe     short loc_140005A4B
0x140005a08  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a0f  lea     rax, WPP_GLOBAL_Control
0x140005a16  cmp     rcx, rax
0x140005a19  jz      loc_1400058AF
0x140005a1f  cmp     byte ptr [rcx+29h], 2
0x140005a23  jb      loc_1400058AF
0x140005a29  mov     rcx, [rcx+18h]
0x140005a2d  lea     r8, WPP_33b5c1abd2bc3b5ab5f1e33a32ecfbc2_Traceguids
0x140005a34  mov     edx, 0Bh
0x140005a39  mov     [rsp+78h+var_58], r12d
0x140005a3e  mov     r9d, r10d
0x140005a41  call    WPP_SF_DD
0x140005a46  jmp     loc_1400058AF
0x140005a4b  mov     edx, eax; unsigned int
0x140005a4d  call    ?AllocateUrb@CTsUrbResult@@IEAAPEAU_URB@@K@Z; CTsUrbResult::AllocateUrb(ulong)
0x140005a52  mov     [rsp+78h+var_48], rax
0x140005a57  mov     rdi, rax
0x140005a5a  test    rax, rax
0x140005a5d  jnz     short loc_140005A69
0x140005a5f  mov     eax, 0C0000017h
0x140005a64  jmp     loc_140005B69
0x140005a69  xor     eax, eax
0x140005a6b  mov     dword ptr [rsp+78h+arg_38], 0
0x140005a76  xorps   xmm0, xmm0
0x140005a79  lea     r14, [rdi+28h]
0x140005a7d  movups  xmmword ptr [rdi], xmm0
0x140005a80  movups  xmmword ptr [rdi+10h], xmm0
0x140005a84  mov     [rdi+20h], rax
0x140005a88  mov     [rdi], bx
0x140005a8b  movzx   eax, word ptr [rbp+2]
0x140005a8f  mov     [rdi+2], ax
0x140005a93  cmp     dword ptr [rbp+0Ch], 0
0x140005a97  jbe     loc_140005B34
0x140005a9d  mov     edi, dword ptr [rsp+78h+arg_38]
0x140005aa4  movzx   eax, word ptr [r15+2]
0x140005aa9  xor     edx, edx; Val
0x140005aab  inc     eax
0x140005aad  mov     rcx, r14; void *
0x140005ab0  lea     eax, [rax+rax*2]
0x140005ab3  shl     eax, 3
0x140005ab6  mov     r8d, eax; Size
0x140005ab9  mov     ebx, eax
0x140005abb  call    memset
0x140005ac0  mov     [r14], bx
0x140005ac4  xor     r8d, r8d
0x140005ac7  mov     al, [r15+4]
0x140005acb  mov     [r14+2], al
0x140005acf  mov     al, [r15+5]
0x140005ad3  mov     [r14+3], al
0x140005ad7  mov     eax, [r15+8]
0x140005adb  mov     [r14+10h], eax
0x140005adf  cmp     [r15+8], r8d
0x140005ae3  jbe     short loc_140005B16
0x140005ae5  lea     rdx, [r8+r8*2]
0x140005ae9  movzx   eax, word ptr [r15+rdx*4+0Ch]
0x140005aef  lea     rcx, [r8+r8*2]
0x140005af3  mov     [r14+rcx*8+18h], ax
0x140005af9  inc     r8d
0x140005afc  mov     eax, [r15+rdx*4+10h]
0x140005b01  mov     [r14+rcx*8+28h], eax
0x140005b06  mov     eax, [r15+rdx*4+14h]
0x140005b0b  mov     [r14+rcx*8+2Ch], eax
0x140005b10  cmp     r8d, [r15+8]
0x140005b14  jb      short loc_140005AE5
0x140005b16  movzx   eax, word ptr [r14]
0x140005b1a  inc     edi
0x140005b1c  add     r14, rax
0x140005b1f  movzx   eax, word ptr [r15]
0x140005b23  add     r15, rax
0x140005b26  cmp     edi, [rbp+0Ch]
0x140005b29  jb      loc_140005AA4
0x140005b2f  mov     rdi, [rsp+78h+var_48]
0x140005b34  test    rsi, rsi
0x140005b37  jz      short loc_140005B4E
0x140005b39  movzx   ecx, word ptr [rdi]
0x140005b3c  mov     rdx, rsi; Src
0x140005b3f  add     rcx, rdi; void *
0x140005b42  mov     r8d, r13d; Size
0x140005b45  mov     [rdi+18h], rcx
0x140005b49  call    memmove
0x140005b4e  mov     rcx, [rsp+78h+arg_0]
0x140005b56  mov     [rcx+6AAh], r12w
0x140005b5e  mov     al, [rbp+0Ch]
0x140005b61  mov     [rcx+6B8h], al
0x140005b67  xor     eax, eax
0x140005b69  mov     rbx, [rsp+78h+arg_8]
0x140005b71  add     rsp, 40h
0x140005b75  pop     r15
0x140005b77  pop     r14
0x140005b79  pop     r13
0x140005b7b  pop     r12
0x140005b7d  pop     rdi
0x140005b7e  pop     rsi
0x140005b7f  pop     rbp
0x140005b80  retn
```
