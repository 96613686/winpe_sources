# DumpAndValidateGenericDescriptor

- ea: `0x14003580c`
- end: `0x140035991`
- name: `DumpAndValidateGenericDescriptor`
- size: `389`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14002f2e0`
- `0x14002f3e8`
- `0x14002f590`
- `0x14002f8cc`
- `0x14002fd58`

## callees

- `0x140004bac`
- `0x14001b118`
- `0x14001b15c`
- `0x14003580c`
- `0x140038ae4`

## pseudocode

```c
__int64 __fastcall DumpAndValidateGenericDescriptor(unsigned __int8 *a1, unsigned __int64 a2)
{
  unsigned __int8 *v4; // rcx
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  __int64 i; // rsi
  unsigned int j; // ebp

  if ( (unsigned int)Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline() )
  {
    if ( (unsigned __int64)a1 > a2 || a2 - (unsigned __int64)a1 < *a1 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return 3221225473LL;
      v6 = 10;
      goto LABEL_31;
    }
  }
  else
  {
    v4 = &a1[*a1];
    if ( v4 <= a1 || (unsigned __int64)v4 > a2 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return 3221225473LL;
      v6 = 11;
LABEL_31:
      WPP_SF_(v5->AttachedDevice, v6, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
      return 3221225473LL;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1);
  }
  for ( i = 0; (unsigned int)i < *a1; i = (unsigned int)(i + 1) )
  {
    for ( j = 0; j < 0x10; ++j )
    {
      if ( (unsigned int)i >= *a1 )
        break;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[i]);
      i = (unsigned int)(i + 1);
    }
    if ( (unsigned int)i < *a1
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids, a1[i]);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14003580c  push    rbx
0x14003580e  push    rbp
0x14003580f  push    rsi
0x140035810  push    rdi
0x140035811  sub     rsp, 28h
0x140035815  mov     rdi, rdx
0x140035818  mov     rbx, rcx
0x14003581b  call    Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline
0x140035820  test    eax, eax
0x140035822  jnz     short loc_14003585F
0x140035824  movzx   ecx, byte ptr [rbx]
0x140035827  add     rcx, rbx
0x14003582a  cmp     rcx, rbx
0x14003582d  jbe     short loc_140035834
0x14003582f  cmp     rcx, rdi
0x140035832  jbe     short loc_140035877
0x140035834  mov     rcx, cs:WPP_GLOBAL_Control
0x14003583b  lea     rdi, WPP_GLOBAL_Control
0x140035842  cmp     rcx, rdi
0x140035845  jz      loc_140035982
0x14003584b  cmp     byte ptr [rcx+29h], 2
0x14003584f  jb      loc_140035982
0x140035855  mov     edx, 0Bh
0x14003585a  jmp     loc_140035972
0x14003585f  cmp     rbx, rdi
0x140035862  ja      loc_140035954
0x140035868  movzx   eax, byte ptr [rbx]
0x14003586b  sub     rdi, rbx
0x14003586e  cmp     rdi, rax
0x140035871  jb      loc_140035954
0x140035877  mov     rcx, cs:WPP_GLOBAL_Control
0x14003587e  lea     rdi, WPP_GLOBAL_Control
0x140035885  cmp     rcx, rdi
0x140035888  jz      short loc_1400358CF
0x14003588a  cmp     byte ptr [rcx+29h], 5
0x14003588e  jb      short loc_1400358A5
0x140035890  mov     rcx, [rcx+18h]
0x140035894  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x14003589b  mov     edx, 0Ch
0x1400358a0  call    WPP_SF_
0x1400358a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400358ac  cmp     rcx, rdi
0x1400358af  jz      short loc_1400358CF
0x1400358b1  cmp     byte ptr [rcx+29h], 5
0x1400358b5  jb      short loc_1400358CF
0x1400358b7  mov     rcx, [rcx+18h]
0x1400358bb  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x1400358c2  mov     edx, 0Dh
0x1400358c7  mov     r9, rbx
0x1400358ca  call    WPP_SF_q
0x1400358cf  xor     esi, esi
0x1400358d1  cmp     [rbx], sil
0x1400358d4  jbe     short loc_140035950
0x1400358d6  xor     ebp, ebp
0x1400358d8  movzx   eax, byte ptr [rbx]
0x1400358db  cmp     esi, eax
0x1400358dd  jnb     short loc_140035914
0x1400358df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400358e6  cmp     rcx, rdi
0x1400358e9  jz      short loc_14003590B
0x1400358eb  cmp     byte ptr [rcx+29h], 5
0x1400358ef  jb      short loc_14003590B
0x1400358f1  movzx   r9d, byte ptr [rsi+rbx]
0x1400358f6  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x1400358fd  mov     rcx, [rcx+18h]
0x140035901  mov     edx, 0Eh
0x140035906  call    WPP_SF_d
0x14003590b  inc     ebp
0x14003590d  inc     esi
0x14003590f  cmp     ebp, 10h
0x140035912  jb      short loc_1400358D8
0x140035914  movzx   eax, byte ptr [rbx]
0x140035917  cmp     esi, eax
0x140035919  jnb     short loc_140035947
0x14003591b  mov     rcx, cs:WPP_GLOBAL_Control
0x140035922  cmp     rcx, rdi
0x140035925  jz      short loc_140035947
0x140035927  cmp     byte ptr [rcx+29h], 5
0x14003592b  jb      short loc_140035947
0x14003592d  movzx   r9d, byte ptr [rsi+rbx]
0x140035932  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x140035939  mov     rcx, [rcx+18h]
0x14003593d  mov     edx, 0Fh
0x140035942  call    WPP_SF_d
0x140035947  movzx   eax, byte ptr [rbx]
0x14003594a  inc     esi
0x14003594c  cmp     esi, eax
0x14003594e  jb      short loc_1400358D6
0x140035950  xor     eax, eax
0x140035952  jmp     short loc_140035987
0x140035954  mov     rcx, cs:WPP_GLOBAL_Control
0x14003595b  lea     rdi, WPP_GLOBAL_Control
0x140035962  cmp     rcx, rdi
0x140035965  jz      short loc_140035982
0x140035967  cmp     byte ptr [rcx+29h], 2
0x14003596b  jb      short loc_140035982
0x14003596d  mov     edx, 0Ah
0x140035972  mov     rcx, [rcx+18h]
0x140035976  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x14003597d  call    WPP_SF_
0x140035982  mov     eax, 0C0000001h
0x140035987  add     rsp, 28h
0x14003598b  pop     rdi
0x14003598c  pop     rsi
0x14003598d  pop     rbp
0x14003598e  pop     rbx
0x14003598f  retn
```
