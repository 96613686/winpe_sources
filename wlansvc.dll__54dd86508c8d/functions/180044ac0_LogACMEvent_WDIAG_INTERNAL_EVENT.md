# LogACMEvent(_WDIAG_INTERNAL_EVENT *)

- ea: `0x180044ac0`
- end: `0x180045ed4`
- name: `?LogACMEvent@@YAXPEAU_WDIAG_INTERNAL_EVENT@@@Z`
- size: `5140`
- prototype: `void __fastcall(struct _WDIAG_INTERNAL_EVENT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180011558`

## callees

- `0x180044ac0`
- `0x180045ee0`
- `0x1800469dc`

## string_xrefs

- `0x180044d35`: `wlan_notification_acm_scan_complete`
- `0x180045a3d`: `wlan_notification_acm_connection_complete`
- `0x1800456d0`: `wlan_notification_msm_private_association_completed`
- `0x180044af9`: `eACM_EVENT_MSM_SET_HIDDEN_SSID_LIST`
- `0x180044b00`: `# of Hidden SSIDs`
- `0x180044c0c`: `wlan_notification_msm_link_state_change`
- `0x180044d54`: `SERVICE_CONTROL_DEVICEEVENT`
- `0x180044dd9`: `SERVICE_CONTROL_POWEREVENT`
- `0x180044ec1`: `L2_NOTIFICATION_SOURCE_SECURITY`
- `0x180044f56`: `SERVICE_CONTROL_SESSIONCHANGE`
- `0x180045a49`: `wlan_notification_acm_connection_attempt_fail`
- `0x180045440`: `wlan_notification_security_start`
- `0x180045434`: `wlan_notification_security_end`
- `0x1800450ae`: `SERVICE_CONTROL_CONTINUE`
- `0x1800450ba`: `SERVICE_CONTROL_INTERROGATE`
- `0x180045096`: `SERVICE_CONTROL_STOP`
- `0x1800450a2`: `SERVICE_CONTROL_PAUSE`
- `0x1800450de`: `SERVICE_CONTROL_NETBINDADD`
- `0x1800450ea`: `SERVICE_CONTROL_NETBINDREMOVE`
- `0x1800450c6`: `SERVICE_CONTROL_SHUTDOWN`
- `0x1800450d2`: `SERVICE_CONTROL_PARAMCHANGE`
- `0x18004510e`: `SERVICE_CONTROL_HARDWAREPROFILECHANGE`
- `0x1800450f6`: `SERVICE_CONTROL_NETBINDENABLE`
- `0x180045102`: `SERVICE_CONTROL_NETBINDDISABLE`
- `0x180045132`: `SERVICE_CONTROL_TRIGGEREVENT`
- `0x18004513e`: `SERVICE_CONTROL_LOWRESOURCES`
- `0x18004511a`: `SERVICE_CONTROL_PRESHUTDOWN`
- `0x180045126`: `SERVICE_CONTROL_TIMECHANGE`
- `0x180045162`: `SERVICE_CONTROL_ ?`
- `0x18004514a`: `SERVICE_CONTROL_SYSTEMLOWRESOURCES`
- `0x180045156`: `WLANSVC_CUSTOM_SERVICE_CONTROL_COMPLETE_MIGRATION`
- `0x180045b65`: `wlan_notification_acm_private_anqp_cache_change`
- `0x180045544`: `wlan_notification_msm_link_degraded`
- `0x180045550`: `wlan_notification_msm_link_improved`
- `0x18004561c`: `wlan_notification_msm_private_wfd_incoming_invitation_request`
- `0x180045628`: `wlan_notification_msm_private_wfd_gon_completed`
- `0x180045610`: `wlan_notification_msm_private_wfd_incoming_gon_request`
- `0x180045634`: `wlan_notification_msm_private_wfd_invitation_completed`
- `0x180045664`: `wlan_notification_msm_private_wfd_incoming_provision_discovery_request`
- `0x180045670`: `wlan_notification_msm_private_wfd_provision_discovery_completed`
- `0x180045694`: `wlan_notification_msm_private_anqp_query_completed`
- `0x1800456ac`: `wlan_notification_msm_private_wfd_visible_device_list_updated`
- `0x1800456b8`: `wlan_notification_msm_private_wfd_operating_channel_attributes_updated`
- `0x1800458b7`: `MSMSEC_NOTIFICATION_PMKCACHE_ADD`
- `0x1800458c3`: `MSMSEC_NOTIFICATION_PMKCACHE_UPDATE`
- `0x1800458cf`: `MSMSEC_NOTIFICATION_PMKCACHE_DEL`
- `0x1800457b1`: `OneXNotificationTypeResultUpdate`
- `0x18004585b`: `OneXRestartReasonOneXConfigurationChanged`
- `0x180045414`: `WLAN_NOTIFICATION_SOURCE_SECURITY`
- `0x180045428`: `wlan_notification_security_ ?`
- `0x1800452f2`: `AutoConfig enabled ?`
- `0x180045360`: `eACM_EVENT_MSM_DISCOVER_COMPLETION`
- `0x18004536b`: `eACM_EVENT_MSM_CONNECT_COMPLETION`
- `0x1800453ab`: `eACM_EVENT_PROFILE_UPDATE`

## pseudocode

```c
void __fastcall LogACMEvent(struct _WDIAG_INTERNAL_EVENT *a1)
{
  int v1; // r10d
  const wchar_t *v2; // r9
  unsigned int v3; // r11d
  unsigned __int64 v4; // rdx
  struct _WDIAG_INTERNAL_EVENT *v5; // r8
  const wchar_t *v6; // rdi
  int v7; // ebx
  const wchar_t *v8; // rsi
  int *v9; // rcx
  const unsigned __int16 *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  __int64 v20; // rsi
  unsigned int *v21; // rcx
  unsigned int v22; // edi
  unsigned int v23; // eax
  unsigned int v24; // eax
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx

  v1 = *(_DWORD *)a1;
  v2 = (const wchar_t *)L" ";
  LOBYTE(v3) = 0;
  LOBYTE(v4) = 0;
  v5 = a1;
  v6 = (const wchar_t *)L" ";
  if ( *(_DWORD *)a1 == 1 )
  {
    v9 = (int *)*((_QWORD *)a1 + 8);
    v7 = *v9;
    if ( *v9 == 8 )
    {
      v3 = v9[1];
      v8 = L"WLAN_NOTIFICATION_SOURCE_ACM";
      if ( v3 == 65539 )
      {
        v2 = L"wlan_notification_acm_private_client_rundown";
      }
      else if ( v3 == 65538 )
      {
        v2 = L"wlan_notification_acm_private_profile_status_timeout";
      }
      else if ( v3 > 0x10002 )
      {
        switch ( v3 )
        {
          case 0x10004u:
            v2 = L"wlan_notification_acm_private_gp_settings_change";
            break;
          case 0x10005u:
            v2 = L"wlan_notification_acm_private_profile_name_change";
            break;
          case 0x10006u:
            v2 = L"wlan_notification_acm_private_profile_userdata_change";
            break;
          case 0x10007u:
            v2 = L"wlan_notification_acm_private_anqp_cache_change";
            break;
          case 0x10008u:
            v2 = L"wlan_notification_acm_private_protected_scenario_state_change";
            break;
          case 0x10009u:
            v2 = L"wlan_notification_acm_private_connected_standby_change";
            break;
          default:
LABEL_36:
            v2 = L"wlan_notification_acm_ ?";
            break;
        }
      }
      else
      {
        switch ( v3 )
        {
          case 0u:
            goto LABEL_67;
          case 1u:
            v2 = L"wlan_notification_acm_autoconf_enabled";
            break;
          case 2u:
            v2 = L"wlan_notification_acm_autoconf_disabled";
            break;
          case 3u:
            v2 = L"wlan_notification_acm_background_scan_enabled";
            break;
          case 4u:
            v2 = L"wlan_notification_acm_background_scan_disabled";
            break;
          case 5u:
            v2 = L"wlan_notification_acm_bss_type_change";
            break;
          case 6u:
            v2 = L"wlan_notification_acm_power_setting_change";
            break;
          case 7u:
            v2 = L"wlan_notification_acm_scan_complete";
            break;
          case 8u:
            v2 = L"wlan_notification_acm_scan_fail";
            break;
          case 9u:
            v2 = L"wlan_notification_acm_connection_start";
            break;
          case 0xAu:
            v2 = L"wlan_notification_acm_connection_complete";
            break;
          case 0xBu:
            v2 = L"wlan_notification_acm_connection_attempt_fail";
            break;
          case 0xCu:
            v2 = L"wlan_notification_acm_filter_list_change";
            break;
          case 0xDu:
            v2 = L"wlan_notification_acm_interface_arrival";
            break;
          case 0xEu:
            v2 = L"wlan_notification_acm_interface_removal";
            break;
          case 0xFu:
            v2 = L"wlan_notification_acm_profile_change";
            break;
          case 0x10u:
            v2 = L"wlan_notification_acm_profile_name_change";
            break;
          case 0x11u:
            v2 = L"wlan_notification_acm_profiles_exhausted";
            break;
          case 0x12u:
            v2 = L"wlan_notification_acm_network_not_available";
            break;
          case 0x13u:
            v2 = L"wlan_notification_acm_network_available";
            break;
          case 0x14u:
            v2 = L"wlan_notification_acm_disconnecting";
            break;
          case 0x15u:
            v2 = L"wlan_notification_acm_disconnected";
            break;
          case 0x16u:
            v2 = L"wlan_notification_acm_adhoc_network_state_change";
            break;
          case 0x17u:
            v2 = L"wlan_notification_acm_profile_unblocked";
            break;
          case 0x18u:
            v2 = L"wlan_notification_acm_screen_power_change";
            break;
          case 0x19u:
            v2 = L"wlan_notification_acm_profile_blocked";
            break;
          case 0x1Au:
            v2 = L"wlan_notification_acm_scan_list_refresh";
            break;
          case 0x1Bu:
            v17 = **((_DWORD **)v9 + 4);
            if ( v17 == 1 )
            {
              v6 = L"WiFiOff";
              goto LABEL_67;
            }
            if ( !v17 )
              goto LABEL_285;
            v37 = v17 - 2;
            if ( v37 )
            {
              v38 = v37 - 1;
              if ( v38 )
              {
                if ( v38 == 1 )
                  v6 = L"WiFiGoingOn";
                else
LABEL_285:
                  v6 = L"WiFiStateUnknown";
              }
              else
              {
                v6 = L"WiFiGoingOff";
              }
            }
            else
            {
              v6 = L"WiFiOn";
            }
LABEL_67:
            v2 = L"wlan_notification_acm_start";
            break;
          case 0x1Du:
            v2 = L"wlan_notification_acm_ap_starting";
            break;
          case 0x1Eu:
            v2 = L"wlan_notification_acm_ap_started";
            break;
          case 0x1Fu:
            v2 = L"wlan_notification_acm_ap_start_failure";
            break;
          case 0x20u:
            v2 = L"wlan_notification_acm_ap_stopping";
            break;
          case 0x21u:
            v2 = L"wlan_notification_acm_ap_stopped";
            break;
          default:
            goto LABEL_36;
        }
      }
    }
    else
    {
      switch ( v7 )
      {
        case 16:
          v3 = v9[1];
          v8 = L"WLAN_NOTIFICATION_SOURCE_MSM";
          if ( v3 == 59 )
          {
            v2 = L"wlan_notification_msm_link_state_change";
            v4 = (**((_QWORD **)v9 + 4) + *(_QWORD *)(*((_QWORD *)v9 + 4) + 8LL)) / 0x7D0uLL;
          }
          else if ( v3 == 65552 )
          {
            v2 = L"wlan_notification_msm_private_nic_quiet";
          }
          else if ( v3 > 0x10001 )
          {
            switch ( v3 )
            {
              case 0x10002u:
                v2 = L"wlan_notification_msm_private_port_up";
                break;
              case 0x10003u:
                v2 = L"wlan_notification_msm_private_port_down";
                break;
              case 0x10004u:
                v2 = L"wlan_notification_msm_private_system_resume";
                break;
              case 0x10005u:
                v2 = L"wlan_notification_msm_private_wfd_incoming_gon_request";
                break;
              case 0x10006u:
                v2 = L"wlan_notification_msm_private_wfd_incoming_invitation_request";
                break;
              case 0x10007u:
                v2 = L"wlan_notification_msm_private_wfd_gon_completed";
                break;
              case 0x10008u:
                v2 = L"wlan_notification_msm_private_wfd_invitation_completed";
                break;
              case 0x10009u:
                v2 = L"wlan_notification_msm_private_wfd_go_peer_associated";
                break;
              case 0x1000Au:
                v2 = L"wlan_notification_msm_private_wfd_go_peer_disassociated";
                break;
              case 0x1000Bu:
                v2 = L"wlan_notification_msm_private_wfd_operating_channel_changed";
                break;
              case 0x1000Cu:
                v2 = L"wlan_notification_msm_private_wfd_incoming_provision_discovery_request";
                break;
              case 0x1000Du:
                v2 = L"wlan_notification_msm_private_wfd_provision_discovery_completed";
                break;
              case 0x1000Eu:
                v2 = L"wlan_notification_msm_private_nlo_discovery";
                break;
              case 0x1000Fu:
                v2 = L"wlan_notification_msm_private_nic_active";
                break;
              case 0x10011u:
                v2 = L"wlan_notification_msm_private_wfd_client_associated";
                break;
              case 0x10012u:
                v2 = L"wlan_notification_msm_private_anqp_query_completed";
                break;
              case 0x10013u:
                v2 = L"wlan_notification_msm_private_association_failed";
                break;
              case 0x10014u:
                v2 = L"wlan_notification_msm_private_wfd_visible_device_list_updated";
                break;
              case 0x10015u:
                v2 = L"wlan_notification_msm_private_wfd_operating_channel_attributes_updated";
                break;
              case 0x10016u:
                v2 = L"wlan_notification_msm_private_wfd_provision_discovery_deferred";
                break;
              case 0x10017u:
                v2 = L"wlan_notification_msm_private_association_completed";
                break;
              case 0x10018u:
                v2 = L"wlan_notification_msm_private_ftm_response";
                break;
              default:
LABEL_214:
                v2 = L"wlan_notification_msm_ ?";
                break;
            }
          }
          else if ( v3 == 65537 )
          {
            v2 = L"wlan_notification_msm_private_preassociated";
          }
          else
          {
            switch ( v3 )
            {
              case 0u:
                v2 = L"wlan_notification_msm_start";
                goto LABEL_4;
              case 1u:
                v2 = L"wlan_notification_msm_associating";
                goto LABEL_4;
              case 2u:
                v2 = L"wlan_notification_msm_associated";
                goto LABEL_4;
              case 3u:
                v2 = L"wlan_notification_msm_authenticating";
                goto LABEL_4;
              case 4u:
                v2 = L"wlan_notification_msm_connected";
                goto LABEL_4;
              case 5u:
                v2 = L"wlan_notification_msm_roaming_start";
                goto LABEL_4;
              case 6u:
                v2 = L"wlan_notification_msm_roaming_end";
                goto LABEL_4;
              case 7u:
                v2 = L"wlan_notification_msm_radio_state_change:PhyIndex";
                if ( (unsigned int)v9[6] < 0xC )
                  goto LABEL_4;
                v21 = (unsigned int *)*((_QWORD *)v9 + 4);
                v22 = v21[2];
                v3 = *v21;
                switch ( v22 )
                {
                  case 0u:
                    goto LABEL_168;
                  case 1u:
                    v23 = v21[1];
                    LOBYTE(v4) = 1;
                    if ( v23 )
                    {
                      v24 = v23 - 1;
                      if ( !v24 )
                      {
                        v6 = L"SoftwareRadioON";
                        goto LABEL_4;
                      }
                      if ( v24 == 1 )
                      {
                        v6 = L"SoftwareRadioOFF";
                        goto LABEL_4;
                      }
                    }
                    v6 = L"SoftwareRadioUnknown";
                    break;
                  case 2u:
                    LODWORD(v4) = v21[1];
                    v6 = L"HardwareRadioOFF";
                    break;
                  default:
LABEL_168:
                    LODWORD(v4) = v21[1];
                    v6 = L"HardwareRadioStateUnknown";
                    break;
                }
                break;
              case 8u:
                v2 = L"wlan_notification_msm_signal_quality_change";
                LODWORD(v4) = **((_DWORD **)v9 + 4);
                goto LABEL_4;
              case 9u:
                v2 = L"wlan_notification_msm_disassociating";
                goto LABEL_4;
              case 0xAu:
                v2 = L"wlan_notification_msm_disconnected";
                goto LABEL_4;
              case 0xBu:
                v2 = L"wlan_notification_msm_peer_join";
                goto LABEL_4;
              case 0xCu:
                v2 = L"wlan_notification_msm_peer_leave";
                goto LABEL_4;
              case 0xDu:
                v2 = L"wlan_notification_msm_adapter_removal";
                goto LABEL_4;
              case 0xEu:
                v2 = L"wlan_notification_msm_adapter_operation_mode_change";
                goto LABEL_4;
              case 0xFu:
                v2 = L"wlan_notification_msm_link_degraded";
                goto LABEL_4;
              case 0x10u:
                v2 = L"wlan_notification_msm_link_improved";
                goto LABEL_4;
              case 0x12u:
                v2 = L"wlan_notification_msm_ap_starting";
                goto LABEL_4;
              case 0x13u:
                v2 = L"wlan_notification_msm_ap_started";
                goto LABEL_4;
              case 0x14u:
                v2 = L"wlan_notification_msm_ap_stopping";
                goto LABEL_4;
              case 0x15u:
                v2 = L"wlan_notification_msm_ap_client_associated";
                goto LABEL_4;
              case 0x16u:
                v2 = L"wlan_notification_msm_ap_client_disassociated";
                goto LABEL_4;
              case 0x17u:
                v2 = L"wlan_notification_msm_ap_stopped";
                goto LABEL_4;
              case 0x18u:
                v2 = L"wlan_notification_msm_ap_can_sustain";
                goto LABEL_4;
              case 0x19u:
                v2 = L"wlan_notification_msm_ap_frequency_adopted";
                goto LABEL_4;
              case 0x1Au:
                v2 = L"wlan_notification_msm_vsta_request";
                goto LABEL_4;
              case 0x1Bu:
                v2 = L"wlan_notification_msm_vsta_release";
                goto LABEL_4;
              case 0x1Cu:
                v2 = L"wlan_notification_msm_vsta_conn_data";
                goto LABEL_4;
              default:
                goto LABEL_214;
            }
          }
          break;
        case 64:
          v3 = v9[1];
          v8 = L"WLAN_NOTIFICATION_SOURCE_IHV";
          v2 = L"IHV ?";
          break;
        case 2:
          v3 = v9[1];
          v8 = L"L2_NOTIFICATION_SOURCE_SECURITY";
          if ( v3 == 65537 )
          {
            v2 = L"MSMSEC_NOTIFICATION_INTF_STATE_CHANGE";
            v16 = *(_DWORD *)(*((_QWORD *)v9 + 4) + 16LL);
            LOBYTE(v4) = v16;
            if ( v16 == 1 )
            {
              v6 = L"MSMSEC_ADAPTER_STATE_INITIALIZED";
            }
            else
            {
              v35 = v16 - 2;
              if ( v35 )
              {
                v36 = v35 - 1;
                if ( v36 )
                {
                  if ( v36 == 1 )
                    v6 = L"MSMSEC_ADAPTER_STATE_FAILURE";
                  else
                    v6 = L"MSMSEC_ADAPTER_STATE_ ?";
                }
                else
                {
                  v6 = L"MSMSEC_ADAPTER_STATE_WAIT_FOR_UI";
                }
              }
              else
              {
                v6 = L"MSMSEC_ADAPTER_STATE_PREASSOC_DONE";
              }
            }
          }
          else if ( v3 == 65538 )
          {
            v2 = L"MSMSEC_NOTIFICATION_PORT_STATE_CHANGE";
            v18 = *(_DWORD *)(*((_QWORD *)v9 + 4) + 20LL);
            LOBYTE(v4) = v18;
            if ( v18 == 1 )
            {
              v6 = L"MSMSEC_STATE_NOT_STARTED";
            }
            else
            {
              v32 = v18 - 2;
              if ( v32 )
              {
                v33 = v32 - 1;
                if ( v33 )
                {
                  v34 = v33 - 1;
                  if ( v34 )
                  {
                    if ( v34 == 1 )
                      v6 = L"MSMSEC_STATE_FAILURE";
                    else
                      v6 = L"MSMSEC_STATE_ ?";
                  }
                  else
                  {
                    v6 = L"MSMSEC_STATE_SUCCESS";
                  }
                }
                else
                {
                  v6 = L"MSMSEC_STATE_EXCHANGING_KEYS";
                }
              }
              else
              {
                v6 = L"MSMSEC_STATE_AUTHENTICATING";
              }
            }
          }
          else
          {
            switch ( v3 )
            {
              case 0x10003u:
                v2 = L"MSMSEC_NOTIFICATION_PMKCACHE_ADD";
                break;
              case 0x10004u:
                v2 = L"MSMSEC_NOTIFICATION_PMKCACHE_UPDATE";
                break;
              case 0x10005u:
                v2 = L"MSMSEC_NOTIFICATION_PMKCACHE_DEL";
                break;
              case 0x10006u:
                v2 = L"MSMSEC_NOTIFICATION_PREAUTH_BEGIN";
                break;
              case 0x10007u:
                v2 = L"MSMSEC_NOTIFICATION_PREAUTH_END";
                break;
              case 0x10008u:
                v2 = L"MSMSEC_NOTIFICATION_PSK_MISMATCH";
                break;
              case 0x10009u:
                v2 = L"MSMSEC_NOTIFICATION_EAP_ERROR";
                break;
              default:
                v2 = L"MSMSEC_NOTIFICATION_ ?";
                break;
            }
          }
          break;
        case 4:
          v3 = v9[1];
          v8 = L"L2_NOTIFICATION_SOURCE_ONEX";
          switch ( v3 )
          {
            case 0x10001u:
              v2 = L"OneXPrivateNotificationTypeStateTransition";
              break;
            case 2u:
              v2 = L"OneXNotificationTypeAuthRestarted";
              v19 = **((_DWORD **)v9 + 4);
              LOBYTE(v4) = v19;
              if ( v19 )
              {
                switch ( v19 )
                {
                  case 1:
                    v6 = L"OneXRestartReasonMsmInitiated";
                    break;
                  case 2:
                    v6 = L"OneXRestartReasonOneXHeldStateTimeout";
                    break;
                  case 3:
                    v6 = L"OneXRestartReasonOneXAuthTimeout";
                    break;
                  case 4:
                    v6 = L"OneXRestartReasonOneXConfigurationChanged";
                    break;
                  case 5:
                    v6 = L"OneXRestartReasonOneXUserChanged";
                    break;
                  case 6:
                    v6 = L"OneXRestartReasonQuarantineStateChanged";
                    break;
                  case 7:
                    v6 = L"OneXRestartReasonAltCredsTrial";
                    break;
                  default:
                    v6 = L"OneXRestartReason ?";
                    break;
                }
              }
              else
              {
                v6 = L"OneXRestartReasonPeerInitiated";
              }
              break;
            case 1u:
              v2 = L"OneXNotificationTypeResultUpdate";
              v28 = **((_DWORD **)v9 + 4);
              LOBYTE(v4) = v28;
              if ( v28 )
              {
                v29 = v28 - 1;
                if ( v29 )
                {
                  v30 = v29 - 1;
                  if ( v30 )
                  {
                    v31 = v30 - 1;
                    if ( v31 )
                    {
                      if ( v31 == 1 )
                        v6 = L"OneXAuthFailure";
                      else
                        v6 = L"OneXAuth ?";
                    }
                    else
                    {
                      v6 = L"OneXAuthSuccess";
                    }
                  }
                  else
                  {
                    v6 = L"OneXAuthNoAuthenticatorFound";
                  }
                }
                else
                {
                  v6 = L"OneXAuthInProgress";
                }
              }
              else
              {
                v6 = L"OneXAuthNotStarted";
              }
              break;
            case 0x10002u:
              v2 = L"OneXPrivateNotificationTypeNetworkInfo";
              break;
            case 0x10003u:
              v2 = L"OneXPrivateNotificationTypeEapAttributes";
              break;
            case 0x10004u:
              v2 = L"OneXPrivateNotificationTypeDiagnosticsHint";
              v25 = *(_DWORD *)(*((_QWORD *)v9 + 4) + 4LL);
              LOBYTE(v4) = v25;
              if ( v25 )
              {
                v26 = v25 - 1;
                if ( v26 )
                {
                  v27 = v26 - 1;
                  if ( v27 )
                  {
                    if ( v27 == 1 )
                      v6 = L"OneXDiagHintAPTimeouts";
                    else
                      v6 = L"OneXDiagHint ?";
                  }
                  else
                  {
                    v6 = L"OneXDiagHintBackendNotResponsive";
                  }
                }
                else
                {
                  v6 = L"OneXDiagHintUserCancellation";
                }
              }
              else
              {
                v6 = L"OneXDiagHintUserNotResponsive";
              }
              break;
            case 0x10005u:
              v2 = L"OneXPrivateNotificationTypeOneXNetwork";
              break;
            default:
              v2 = L"OneXNotificationType ?";
              break;
          }
          break;
        case 32:
          v3 = v9[1];
          v8 = L"WLAN_NOTIFICATION_SOURCE_SECURITY";
          if ( v3 )
          {
            if ( v3 == 1 )
              v2 = L"wlan_notification_security_end";
            else
              v2 = L"wlan_notification_security_ ?";
          }
          else
          {
            v2 = L"wlan_notification_security_start";
          }
          break;
        default:
          v8 = L"WLAN_NOTIFICATION_SOURCE_ ?";
          break;
      }
    }
  }
  else if ( v1 == 6 )
  {
    v7 = *((_DWORD *)a1 + 24);
    v8 = (const wchar_t *)L"# of Hidden SSIDs";
  }
  else
  {
    LOBYTE(v7) = 0;
    v8 = (const wchar_t *)L" ";
    switch ( v1 )
    {
      case 0:
        v7 = *((_DWORD *)a1 + 24);
        v3 = *((_DWORD *)a1 + 25);
        if ( v7 == 11 )
        {
          v8 = L"SERVICE_CONTROL_DEVICEEVENT";
        }
        else if ( v7 == 13 )
        {
          v8 = L"SERVICE_CONTROL_POWEREVENT";
          if ( v3 == 32787 )
          {
            v11 = *((_QWORD *)a1 + 8);
            v2 = L"PBT_POWERSETTINGCHANGE";
            if ( v11 && *(_DWORD *)(v11 + 16) >= 4u )
            {
              v12 = *(_QWORD *)v11 - *(_QWORD *)&GUID_LOW_POWER_EPOCH.Data1;
              LODWORD(v4) = *(_DWORD *)(v11 + 20);
              if ( *(_QWORD *)v11 == *(_QWORD *)&GUID_LOW_POWER_EPOCH.Data1 )
                v12 = *(_QWORD *)(v11 + 8) - *(_QWORD *)GUID_LOW_POWER_EPOCH.Data4;
              if ( v12 )
              {
                v13 = *(_QWORD *)v11 - *(_QWORD *)&GUID_MONITOR_POWER_ON.Data1;
                if ( *(_QWORD *)v11 == *(_QWORD *)&GUID_MONITOR_POWER_ON.Data1 )
                  v13 = *(_QWORD *)(v11 + 8) - *(_QWORD *)GUID_MONITOR_POWER_ON.Data4;
                if ( v13 )
                {
                  v14 = *(_QWORD *)v11 - *(_QWORD *)&GUID_ACDC_POWER_SOURCE.Data1;
                  if ( *(_QWORD *)v11 == *(_QWORD *)&GUID_ACDC_POWER_SOURCE.Data1 )
                    v14 = *(_QWORD *)(v11 + 8) - *(_QWORD *)GUID_ACDC_POWER_SOURCE.Data4;
                  if ( v14 )
                  {
                    v15 = *(_QWORD *)v11 - *(_QWORD *)&GUID_80211_SETTING_PERFORMANCE.Data1;
                    if ( *(_QWORD *)v11 == *(_QWORD *)&GUID_80211_SETTING_PERFORMANCE.Data1 )
                      v15 = *(_QWORD *)(v11 + 8) - *(_QWORD *)GUID_80211_SETTING_PERFORMANCE.Data4;
                    if ( !v15 )
                    {
                      v2 = L"PBT_POWERSETTINGCHANGE: WiFiPerformance";
                      LOBYTE(v4) = 0;
                    }
                  }
                  else if ( (_DWORD)v4 )
                  {
                    if ( (_DWORD)v4 == 1 )
                    {
                      v2 = L"PBT_POWERSETTINGCHANGE: Power=DC";
                    }
                    else if ( (_DWORD)v4 == 2 )
                    {
                      v2 = L"PBT_POWERSETTINGCHANGE: Short-term Power";
                    }
                  }
                  else
                  {
                    v2 = L"PBT_POWERSETTINGCHANGE: Power=AC";
                  }
                }
                else if ( (_DWORD)v4 )
                {
                  if ( (_DWORD)v4 == 1 )
                    v2 = L"PBT_POWERSETTINGCHANGE: Monitor=ON";
                }
                else
                {
                  v2 = L"PBT_POWERSETTINGCHANGE: Monitor=OFF";
                }
              }
              else if ( (_DWORD)v4 )
              {
                if ( (_DWORD)v4 == 1 )
                  v2 = L"PBT_POWERSETTINGCHANGE: CS=Exit";
              }
              else
              {
                v2 = L"PBT_POWERSETTINGCHANGE: CS=Entry";
              }
            }
          }
          else
          {
            switch ( v3 )
            {
              case 0u:
                v2 = L"PBT_APMQUERYSUSPEND";
                break;
              case 1u:
                v2 = L"PBT_APMQUERYSTANDBY";
                break;
              case 2u:
                v2 = L"PBT_APMQUERYSUSPENDFAILED";
                break;
              case 3u:
                v2 = L"PBT_APMQUERYSTANDBYFAILED";
                break;
              case 4u:
                v2 = L"PBT_APMSUSPEND";
                break;
              case 5u:
                v2 = L"PBT_APMSTANDBY";
                break;
              case 6u:
                v2 = L"PBT_APMRESUMECRITICAL";
                break;
              case 7u:
                v2 = L"PBT_APMRESUMESUSPEND";
                break;
              case 8u:
                v2 = L"PBT_APMRESUMESTANDBY";
                break;
              case 9u:
                v2 = L"PBT_APMBATTERYLOW";
                break;
              case 0xAu:
                v2 = L"PBT_APMPOWERSTATUSCHANGE";
                break;
              case 0xBu:
                v2 = L"PBT_APMOEMEVENT";
                break;
              case 0x12u:
                v2 = L"PBT_APMRESUMEAUTOMATIC";
                break;
              default:
                v2 = L"PBT_ ?";
                break;
            }
          }
        }
        else
        {
          switch ( v7 )
          {
            case 1:
              v8 = L"SERVICE_CONTROL_STOP";
              break;
            case 2:
              v8 = L"SERVICE_CONTROL_PAUSE";
              break;
            case 3:
              v8 = L"SERVICE_CONTROL_CONTINUE";
              break;
            case 4:
              v8 = L"SERVICE_CONTROL_INTERROGATE";
              break;
            case 5:
              v8 = L"SERVICE_CONTROL_SHUTDOWN";
              break;
            case 6:
              v8 = L"SERVICE_CONTROL_PARAMCHANGE";
              break;
            case 7:
              v8 = L"SERVICE_CONTROL_NETBINDADD";
              break;
            case 8:
              v8 = L"SERVICE_CONTROL_NETBINDREMOVE";
              break;
            case 9:
              v8 = L"SERVICE_CONTROL_NETBINDENABLE";
              break;
            case 10:
              v8 = L"SERVICE_CONTROL_NETBINDDISABLE";
              break;
            case 12:
              v8 = L"SERVICE_CONTROL_HARDWAREPROFILECHANGE";
              break;
            case 14:
              v8 = L"SERVICE_CONTROL_SESSIONCHANGE";
              if ( v3 == 5 )
              {
                v2 = L"WTS_SESSION_LOGON";
              }
              else
              {
                switch ( v3 )
                {
                  case 1u:
                    v2 = L"WTS_CONSOLE_CONNECT";
                    break;
                  case 2u:
                    v2 = L"WTS_CONSOLE_DISCONNECT";
                    break;
                  case 3u:
                    v2 = L"WTS_REMOTE_CONNECT";
                    break;
                  case 4u:
                    v2 = L"WTS_REMOTE_DISCONNECT";
                    break;
                  case 6u:
                    v2 = L"WTS_SESSION_LOGOFF";
                    break;
                  case 7u:
                    v2 = L"WTS_SESSION_LOCK";
                    break;
                  case 8u:
                    v2 = L"WTS_SESSION_UNLOCK";
                    break;
                  case 9u:
                    v2 = L"WTS_SESSION_REMOTE_CONTROL";
                    break;
                  default:
                    v2 = L"WTS_ ?";
                    break;
                }
              }
              break;
            case 15:
              v8 = L"SERVICE_CONTROL_PRESHUTDOWN";
              break;
            case 16:
              v8 = L"SERVICE_CONTROL_TIMECHANGE";
              break;
            case 32:
              v8 = L"SERVICE_CONTROL_TRIGGEREVENT";
              break;
            case 96:
              v8 = L"SERVICE_CONTROL_LOWRESOURCES";
              break;
            case 97:
              v8 = L"SERVICE_CONTROL_SYSTEMLOWRESOURCES";
              break;
            case 128:
              v8 = L"WLANSVC_CUSTOM_SERVICE_CONTROL_COMPLETE_MIGRATION";
              break;
            default:
              v8 = L"SERVICE_CONTROL_ ?";
              break;
          }
        }
        break;
      case 2:
        v7 = *(_DWORD *)(*((_QWORD *)a1 + 8) + 64LL);
        if ( v7 )
        {
          if ( v7 == 1 )
            v8 = L"Connect SM";
          else
            v8 = L"ace_state_machine_type_ ?";
        }
        else
        {
          v8 = L"Scan SM";
        }
        v10 = AceTriggerToName(*((_QWORD *)a1 + 15));
        v4 = *((unsigned int *)v5 + 34);
        v2 = v10;
        v6 = (const wchar_t *)(&g_strStateName)[v4];
        break;
      case 3:
        v8 = (const wchar_t *)*((_QWORD *)a1 + 8);
        break;
      case 4:
        v7 = *((_DWORD *)a1 + 30);
        v3 = *((_DWORD *)a1 + 24);
        v8 = L"IHV WDI version";
        LODWORD(v4) = *((_DWORD *)a1 + 25);
        v2 = L"AutoConfig enabled ?";
        v6 = L"Background Scan enabled ?";
        break;
      case 8:
      case 9:
        v20 = *((_QWORD *)a1 + 8);
        goto LABEL_147;
      case 10:
      case 11:
        v20 = *((_QWORD *)a1 + 8);
        goto LABEL_147;
      case 13:
      case 14:
      case 23:
        v20 = *((_QWORD *)a1 + 9);
LABEL_147:
        if ( v20 )
          v8 = (const wchar_t *)(v20 + 24);
        else
          v8 = &word_180243548;
        break;
      case 19:
        v7 = *((_DWORD *)a1 + 34);
        v8 = L"Notify Selection List Changed ?";
        break;
      case 24:
        LOBYTE(v3) = g_bPeriodicOrDiagnosticPacketStatsEnabled;
        v8 = L"Is in CS ?";
        LOBYTE(v7) = *((_DWORD *)a1 + 24) == 0;
        v2 = L"Diag Packets Stats Enabled ?";
        break;
      default:
        break;
    }
  }
LABEL_4:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0 )
  {
    WPP_SF_SDSDSDSDii(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v1,
      (__int64)v8,
      v7,
      (__int64)v2,
      v3,
      (__int64)v6,
      v4,
      *((_QWORD *)v5 + 6),
      *((_QWORD *)v5 + 5));
  }
}

```

## disassembly

```asm
0x180044ac0  push    rbx
0x180044ac2  push    rbp
0x180044ac3  push    rsi
0x180044ac4  push    rdi
0x180044ac5  sub     rsp, 78h
0x180044ac9  mov     r10d, [rcx]
0x180044acc  lea     r9, asc_180241B50; " "
0x180044ad3  xor     r11d, r11d
0x180044ad6  mov     [rsp+98h+arg_0], r14
0x180044ade  xor     edx, edx
0x180044ae0  mov     r8, rcx
0x180044ae3  mov     rdi, r9
0x180044ae6  cmp     r10d, 1
0x180044aea  jz      short loc_180044B2B
0x180044aec  cmp     r10d, 6
0x180044af0  jnz     loc_180044BBB
0x180044af6  mov     ebx, [rcx+60h]
0x180044af9  lea     rbp, aEacmEventMsmSe; "eACM_EVENT_MSM_SET_HIDDEN_SSID_LIST"
0x180044b00  lea     rsi, aOfHiddenSsids; "# of Hidden SSIDs"
0x180044b07  mov     rcx, cs:WPP_GLOBAL_Control
0x180044b0e  lea     rax, WPP_GLOBAL_Control
0x180044b15  mov     r14, [rsp+98h+arg_0]
0x180044b1d  cmp     rcx, rax
0x180044b20  jnz     short loc_180044B62
0x180044b22  add     rsp, 78h
0x180044b26  pop     rdi
0x180044b27  pop     rsi
0x180044b28  pop     rbp
0x180044b29  pop     rbx
0x180044b2a  retn
0x180044b2b  mov     rcx, [rcx+40h]
0x180044b2f  lea     rbp, aEacmEventInter; "eACM_EVENT_INTERNAL_NOTIFICATION"
0x180044b36  mov     ebx, [rcx]
0x180044b38  cmp     ebx, 8
0x180044b3b  jnz     loc_180044BEA
0x180044b41  mov     r11d, [rcx+4]
0x180044b45  lea     rsi, aWlanNotificati_30; "WLAN_NOTIFICATION_SOURCE_ACM"
0x180044b4c  cmp     r11d, 10003h
0x180044b53  jnz     loc_180044C39
0x180044b59  lea     r9, aWlanNotificati_55; "wlan_notification_acm_private_client_ru"...
0x180044b60  jmp     short loc_180044B07
0x180044b62  cmp     byte ptr [rcx+0E1h], 3
0x180044b69  jb      short loc_180044B22
0x180044b6b  test    byte ptr [rcx+0E4h], 4
0x180044b72  jz      short loc_180044B22
0x180044b74  mov     rax, [r8+28h]
0x180044b78  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180044b7f  mov     qword ptr [rsp+98h+var_38], rax; char
0x180044b84  mov     rax, [r8+30h]
0x180044b88  mov     qword ptr [rsp+98h+var_40], rax; char
0x180044b8d  mov     dword ptr [rsp+98h+var_48], edx; char
0x180044b91  mov     [rsp+98h+var_50], rdi; __int64
0x180044b96  mov     dword ptr [rsp+98h+var_58], r11d; char
0x180044b9b  mov     [rsp+98h+var_60], r9; __int64
0x180044ba0  mov     r9, rbp
0x180044ba3  mov     dword ptr [rsp+98h+var_68], ebx; char
0x180044ba7  mov     [rsp+98h+var_70], rsi; __int64
0x180044bac  mov     dword ptr [rsp+98h+var_78], r10d; char
0x180044bb1  call    WPP_SF_SDSDSDSDii
0x180044bb6  jmp     loc_180044B22
0x180044bbb  xor     ebx, ebx
0x180044bbd  mov     rsi, r9
0x180044bc0  cmp     r10d, 18h; switch 25 cases
0x180044bc4  ja      def_180044BDC; jumptable 0000000180044BDC default case, cases 1,6,22
0x180044bca  lea     r14, __ImageBase
0x180044bd1  mov     eax, ds:(jpt_180044BDC - 180000000h)[r14+r10*4]
0x180044bd9  add     rax, r14
0x180044bdc  jmp     rax; switch jump
0x180044bde  lea     rbp, aEacmEventMsmGe; jumptable 0000000180044BDC case 7
0x180044be5  jmp     loc_180044B07
0x180044bea  cmp     ebx, 10h
0x180044bed  jnz     loc_180044D09
0x180044bf3  mov     r11d, [rcx+4]
0x180044bf7  lea     rsi, aWlanNotificati_22; "WLAN_NOTIFICATION_SOURCE_MSM"
0x180044bfe  cmp     r11d, 3Bh ; ';'
0x180044c02  jnz     loc_180044CB9
0x180044c08  mov     rax, [rcx+20h]
0x180044c0c  lea     r9, aWlanNotificati_23; "wlan_notification_msm_link_state_change"
0x180044c13  mov     rcx, [rax+8]
0x180044c17  add     rcx, [rax]
0x180044c1a  mov     rax, 624DD2F1A9FBE77h
0x180044c24  mul     rcx
0x180044c27  sub     rcx, rdx
0x180044c2a  shr     rcx, 1
0x180044c2d  add     rdx, rcx
0x180044c30  shr     rdx, 0Ah
0x180044c34  jmp     loc_180044B07
0x180044c39  cmp     r11d, 10002h
0x180044c40  jz      loc_180044D29
0x180044c46  ja      loc_180044D6C
0x180044c4c  cmp     r11d, 21h; switch 34 cases
0x180044c50  ja      def_180044C68; jumptable 0000000180044C68 default case, case 28
0x180044c56  lea     r14, __ImageBase
0x180044c5d  mov     eax, ds:(jpt_180044C68 - 180000000h)[r14+r11*4]
0x180044c65  add     rax, r14
0x180044c68  jmp     rax; switch jump
0x180044c6a  lea     r9, aWlanNotificati_96; jumptable 0000000180044C68 case 26
0x180044c71  jmp     loc_180044B07
0x180044c76  mov     rax, [rcx+40h]; jumptable 0000000180044BDC case 2
0x180044c7a  lea     rbp, aEacmEventState; "eACM_EVENT_STATE_TRANSITION"
0x180044c81  mov     ebx, [rax+40h]
0x180044c84  mov     eax, ebx
0x180044c86  test    ebx, ebx
0x180044c88  jnz     loc_1800452AD
0x180044c8e  lea     rsi, aScanSm; "Scan SM"
0x180044c95  mov     r11d, [rcx+78h]
0x180044c99  mov     rcx, [rcx+78h]; unsigned __int64
0x180044c9d  call    ?AceTriggerToName@@YAPEBG_K@Z; AceTriggerToName(unsigned __int64)
0x180044ca2  mov     edx, [r8+88h]
0x180044ca9  mov     r9, rax
0x180044cac  mov     rdi, ds:rva ?g_strStateName@@3QBQEBGB[r14+rdx*8]; ushort const * const near * const g_strStateName ...
0x180044cb4  jmp     loc_180044B07
0x180044cb9  cmp     r11d, 10010h
0x180044cc0  jz      loc_180044D60
0x180044cc6  cmp     r11d, 10001h
0x180044ccd  ja      loc_180044D88
0x180044cd3  jz      loc_1800455E0
0x180044cd9  cmp     r11d, 1Ch; switch 29 cases
0x180044cdd  ja      def_180044CF5; jumptable 0000000180044CF5 default case, case 17
0x180044ce3  lea     r14, __ImageBase
0x180044cea  mov     eax, ds:(jpt_180044CF5 - 180000000h)[r14+r11*4]
0x180044cf2  add     rax, r14
0x180044cf5  jmp     rax; switch jump
0x180044cf7  mov     rax, [rcx+20h]; jumptable 0000000180044CF5 case 8
0x180044cfb  lea     r9, aWlanNotificati_13; "wlan_notification_msm_signal_quality_ch"...
0x180044d02  mov     edx, [rax]
0x180044d04  jmp     loc_180044B07
0x180044d09  cmp     ebx, 40h ; '@'
0x180044d0c  jnz     loc_180044EB4
0x180044d12  mov     r11d, [rcx+4]
0x180044d16  lea     rsi, aWlanNotificati_40; "WLAN_NOTIFICATION_SOURCE_IHV"
0x180044d1d  lea     r9, aIhv_1; "IHV ?"
0x180044d24  jmp     loc_180044B07
0x180044d29  lea     r9, aWlanNotificati_59; "wlan_notification_acm_private_profile_s"...
0x180044d30  jmp     loc_180044B07
0x180044d35  lea     r9, aWlanNotificati_48; jumptable 0000000180044C68 case 7
0x180044d3c  jmp     loc_180044B07
0x180044d41  mov     ebx, [rcx+60h]; jumptable 0000000180044BDC case 0
0x180044d44  lea     rbp, aEacmEventScmNo; "eACM_EVENT_SCM_NOTIFICATION"
0x180044d4b  mov     r11d, [rcx+64h]
0x180044d4f  cmp     ebx, 0Bh
0x180044d52  jnz     short loc_180044DD0
0x180044d54  lea     rsi, aServiceControl_14; "SERVICE_CONTROL_DEVICEEVENT"
0x180044d5b  jmp     loc_180044B07
0x180044d60  lea     r9, aWlanNotificati_101; "wlan_notification_msm_private_nic_quiet"
0x180044d67  jmp     loc_180044B07
0x180044d6c  lea     eax, [r11-10004h]; switch 6 cases
0x180044d73  cmp     eax, 5
0x180044d76  jbe     loc_180045B2D
0x180044d7c  lea     r9, aWlanNotificati_74; jumptable 0000000180044C68 default case, case 28
0x180044d83  jmp     loc_180044B07
0x180044d88  lea     eax, [r11-10002h]; switch 23 cases
0x180044d8f  cmp     eax, 16h
0x180044d92  ja      def_180044CF5; jumptable 0000000180044CF5 default case, case 17
0x180044d98  lea     r14, __ImageBase
0x180044d9f  mov     eax, ds:(jpt_180044DAA - 180000000h)[r14+rax*4]
0x180044da7  add     rax, r14
0x180044daa  jmp     rax; switch jump
0x180044dac  lea     r9, aWlanNotificati_20; jumptable 0000000180044DAA case 65551
0x180044db3  jmp     loc_180044B07
0x180044db8  lea     r9, aWlanNotificati_25; jumptable 0000000180044C68 case 6
0x180044dbf  jmp     loc_180044B07
0x180044dc4  lea     r9, aWlanNotificati_97; jumptable 0000000180044C68 case 19
0x180044dcb  jmp     loc_180044B07
0x180044dd0  cmp     ebx, 0Dh
0x180044dd3  jnz     loc_180044F34
0x180044dd9  lea     rsi, aServiceControl_0; "SERVICE_CONTROL_POWEREVENT"
0x180044de0  cmp     r11d, 8013h
0x180044de7  jnz     loc_18004516E
0x180044ded  mov     rax, [rcx+40h]
0x180044df1  lea     r9, aPbtPowersettin_0; "PBT_POWERSETTINGCHANGE"
0x180044df8  test    rax, rax
0x180044dfb  jz      loc_180044B07
0x180044e01  cmp     dword ptr [rax+10h], 4
0x180044e05  jb      loc_180044B07
0x180044e0b  mov     rcx, [rax]
0x180044e0e  sub     rcx, qword ptr cs:GUID_LOW_POWER_EPOCH.Data1
0x180044e15  mov     edx, [rax+14h]
0x180044e18  jnz     short loc_180044E25
0x180044e1a  mov     rcx, [rax+8]
0x180044e1e  sub     rcx, qword ptr cs:GUID_LOW_POWER_EPOCH.Data4
0x180044e25  test    rcx, rcx
0x180044e28  jz      loc_18004522D
0x180044e2e  mov     rcx, [rax]
0x180044e31  sub     rcx, qword ptr cs:GUID_MONITOR_POWER_ON.Data1
0x180044e38  jnz     short loc_180044E45
0x180044e3a  mov     rcx, [rax+8]
0x180044e3e  sub     rcx, qword ptr cs:GUID_MONITOR_POWER_ON.Data4
0x180044e45  test    rcx, rcx
0x180044e48  jz      loc_180045252
0x180044e4e  mov     rcx, [rax]
0x180044e51  sub     rcx, qword ptr cs:GUID_ACDC_POWER_SOURCE.Data1
0x180044e58  jnz     short loc_180044E65
0x180044e5a  mov     rcx, [rax+8]
0x180044e5e  sub     rcx, qword ptr cs:GUID_ACDC_POWER_SOURCE.Data4
0x180044e65  test    rcx, rcx
0x180044e68  jz      loc_180045277
0x180044e6e  mov     rcx, [rax]
0x180044e71  sub     rcx, qword ptr cs:GUID_80211_SETTING_PERFORMANCE.Data1
0x180044e78  jnz     short loc_180044E85
0x180044e7a  mov     rcx, [rax+8]
0x180044e7e  sub     rcx, qword ptr cs:GUID_80211_SETTING_PERFORMANCE.Data4
0x180044e85  test    rcx, rcx
0x180044e88  jnz     loc_180044B07
0x180044e8e  lea     r9, aPbtPowersettin_3; "PBT_POWERSETTINGCHANGE: WiFiPerformance"
0x180044e95  xor     edx, edx
0x180044e97  jmp     loc_180044B07
0x180044e9c  lea     rbp, aEacmEventMsmRe; jumptable 0000000180044BDC case 18
0x180044ea3  jmp     loc_180044B07
0x180044ea8  lea     r9, aWlanNotificati; jumptable 0000000180044CF5 case 3
0x180044eaf  jmp     loc_180044B07
0x180044eb4  cmp     ebx, 2
0x180044eb7  jnz     loc_180044FA5
0x180044ebd  mov     r11d, [rcx+4]
0x180044ec1  lea     rsi, aL2Notification_0; "L2_NOTIFICATION_SOURCE_SECURITY"
0x180044ec8  cmp     r11d, 10001h
0x180044ecf  jnz     loc_180044F73
0x180044ed5  mov     rax, [rcx+20h]
0x180044ed9  lea     r9, aMsmsecNotifica_3; "MSMSEC_NOTIFICATION_INTF_STATE_CHANGE"
0x180044ee0  mov     ecx, [rax+10h]
0x180044ee3  mov     edx, ecx
0x180044ee5  cmp     ecx, 1
0x180044ee8  jnz     loc_180045967
0x180044eee  lea     rdi, aMsmsecAdapterS_2; "MSMSEC_ADAPTER_STATE_INITIALIZED"
0x180044ef5  jmp     loc_180044B07
0x180044efa  lea     r9, aWlanNotificati_36; jumptable 0000000180044CF5 case 5
0x180044f01  jmp     loc_180044B07
0x180044f06  lea     r9, aWlanNotificati_32; jumptable 0000000180044CF5 case 14
0x180044f0d  jmp     loc_180044B07
0x180044f12  mov     rax, [rcx+20h]; jumptable 0000000180044C68 case 27
0x180044f16  mov     ecx, [rax]
0x180044f18  cmp     ecx, 1
0x180044f1b  jnz     loc_1800459A6
0x180044f21  lea     rdi, aWifioff; "WiFiOff"
0x180044f28  lea     r9, aWlanNotificati_98; jumptable 0000000180044C68 case 0
0x180044f2f  jmp     loc_180044B07
0x180044f34  lea     eax, [rbx-1]; switch 128 cases
0x180044f37  cmp     eax, 7Fh
0x180044f3a  ja      def_180044F54; jumptable 0000000180044F54 default case, cases 11,13,17-31,33-95,98-127
0x180044f40  movzx   eax, ds:(byte_180045D94 - 180000000h)[r14+rax]
0x180044f49  mov     ecx, ds:(jpt_180044F54 - 180000000h)[r14+rax*4]
0x180044f51  add     rcx, r14
0x180044f54  jmp     rcx; switch jump
0x180044f56  lea     rsi, aServiceControl_18; jumptable 0000000180044F54 case 14
0x180044f5d  cmp     r11d, 5
0x180044f61  jnz     loc_180045014
0x180044f67  lea     r9, aWtsSessionLogo_0; "WTS_SESSION_LOGON"
0x180044f6e  jmp     loc_180044B07
0x180044f73  cmp     r11d, 10002h
0x180044f7a  jnz     loc_180045897
0x180044f80  mov     rax, [rcx+20h]
0x180044f84  lea     r9, aMsmsecNotifica_8; "MSMSEC_NOTIFICATION_PORT_STATE_CHANGE"
0x180044f8b  mov     ecx, [rax+14h]
0x180044f8e  mov     edx, ecx
0x180044f90  cmp     ecx, 1
0x180044f93  jnz     loc_180045917
0x180044f99  lea     rdi, aMsmsecStateNot; "MSMSEC_STATE_NOT_STARTED"
0x180044fa0  jmp     loc_180044B07
0x180044fa5  cmp     ebx, 4
0x180044fa8  jnz     loc_1800453FF
0x180044fae  mov     r11d, [rcx+4]
0x180044fb2  lea     rsi, aL2Notification; "L2_NOTIFICATION_SOURCE_ONEX"
0x180044fb9  cmp     r11d, 10001h
0x180044fc0  jnz     short loc_180044FCE
0x180044fc2  lea     r9, aOnexprivatenot_1; "OneXPrivateNotificationTypeStateTransit"...
0x180044fc9  jmp     loc_180044B07
0x180044fce  cmp     r11d, 2
0x180044fd2  jnz     loc_1800456F4
0x180044fd8  mov     rax, [rcx+20h]
0x180044fdc  lea     r9, aOnexnotificati; "OneXNotificationTypeAuthRestarted"
0x180044fe3  mov     ecx, [rax]
0x180044fe5  mov     edx, ecx
0x180044fe7  test    ecx, ecx
0x180044fe9  jnz     loc_18004581C
0x180044fef  lea     rdi, aOnexrestartrea_3; "OneXRestartReasonPeerInitiated"
0x180044ff6  jmp     loc_180044B07
0x180044ffb  mov     ebx, [rcx+88h]; jumptable 0000000180044BDC case 19
0x180045001  lea     rbp, aEacmEventBuild; "eACM_EVENT_BUILD_SELECTION_LIST"
0x180045008  lea     rsi, aNotifySelectio; "Notify Selection List Changed ?"
0x18004500f  jmp     loc_180044B07
0x180045014  lea     eax, [r11-1]; switch 9 cases
0x180045018  cmp     eax, 8
0x18004501b  ja      short def_180045028; jumptable 0000000180045028 default case, case 5
0x18004501d  mov     eax, ds:(jpt_180045028 - 180000000h)[r14+rax*4]
0x180045025  add     rax, r14
0x180045028  jmp     rax; switch jump
0x18004502a  lea     r9, aWtsSessionLogo; jumptable 0000000180045028 case 6
0x180045031  jmp     loc_180044B07
0x180045036  lea     r9, aWtsConsoleConn; jumptable 0000000180045028 case 1
0x18004503d  jmp     loc_180044B07
0x180045042  lea     r9, aWtsConsoleDisc; jumptable 0000000180045028 case 2
0x180045049  jmp     loc_180044B07
0x18004504e  lea     r9, aWtsRemoteConne; jumptable 0000000180045028 case 3
0x180045055  jmp     loc_180044B07
0x18004505a  lea     r9, aWtsRemoteDisco; jumptable 0000000180045028 case 4
0x180045061  jmp     loc_180044B07
0x180045066  lea     r9, aWtsSessionLock; jumptable 0000000180045028 case 7
0x18004506d  jmp     loc_180044B07
0x180045072  lea     r9, aWtsSessionUnlo; jumptable 0000000180045028 case 8
0x180045079  jmp     loc_180044B07
  ... truncated ...
```
